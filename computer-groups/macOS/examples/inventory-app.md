[title]: # (Inventorying .app Bundles)
[tags]: # (learning mode, macOS)
[priority]: # (101)
# Inventorying .app Bundles

Privilege Manager allows the inventory of macOS .app bundles. These are most likely files already installed on a macOS system that can be found in the Applications folder.
In order for Privilege Manager to inventory .app bundles, the user needs to create a .zip file of the .app bundles and move it outside of the Applications folder. Once the .zip is created and moved, it can be uploaded to Privilege Manager for inventory purposes.

A .zip of an .app bundle when inventoried can contain one or more mach-O binaries. The level of details that can be inventoried automatically depends on the format of and information provided in the Info.plist file.

The examples below show certain steps for the zip and upload process for one type of file, while the inventory examples are shown for

* a readable Info.plist file with an .app bundle containing one mach-O binary.
* a readable Info.plist file with an .app bundle containing more than one mach-O binary.
* a binary Info.plist file that does not provide sufficient details automatically and that will require manual steps to add information to the filter and/or policy.

The __Manage Application__ option is only available on files inside the .zip or .rar compressed archives and not on the .zip or .rar file itself.

## Creating a .zip File

1. Navigate to an .app bundle file inside __/Applications__.
1. Right-click and select __Compress__.
1. Select the created .zip file and move it out of __/Applications__.

## Uploading the .zip File

1. Use __Admin | File Upload__ to start the inventory process.
1. Choose a file to upload and click __Upload File__.

   ![upload](images/inventory/app-upload.png "Upload modal")
1. After uploading a .zip file, click __Go to File Details__.

   ![go to file](images/inventory/app-go-to.png "Use Go to File Details button")
1. On the Resource Explorer page, view all the details available.

   ![alt](images/inventory/app-res-expl.png "Resource Explorer page")

## Creating a Filter from the Inventoried .zip File

1. On the Resource Explorer page under __Known Data | File Inventory__, select __Virtual Disk File Contents__.

   ![alt](images/inventory/app-virtual-disk.png "Resource Explorer page")
   * In the File column the .app bundle name is listed as inventoried.
   * In the Folder column the path/location of the .app bundle is provided.
1. In the __File__ column, click on the .app bundle name.
1. The Resource explorer is now displaying the information for the client item.

   | Info.plist readable | Info.plist non-readable (binary format) |
   | ----- | ----- |
   | ![alt](images/inventory/app-manage-full.png "Resource Explorer page") | ![alt](images/inventory/app-client-item.png "Client item details") |
1. Click __Manage Application__.

   | Info.plist readable | Info.plist non-readable (binary format) |
   | ----- | ----- |
   | ![alt](images/inventory/app-manage-full-filter.png "Manage Application modal to create a filter for the .app bundle") | ![alt](images/inventory/app-manage.png "Manage Application modal to create a filter for the .app bundle") |

   Select any or all of the options on the Manage Application modal.
1. Click __Create Filter__.

   Privilege Manager creates a _Wizard Generated File Specification Filter_ for the .app bundle. This filter can be further customized and added to any policy.

   ![alt](images/inventory/app-filter.png "Wizard Generated File Specification Filter for the .app bundle")

## Uploading a .zip with Two mach-O Binaries

App bundles can contain more than one mach-O binary, which will all be inventoried and accessible via the client items under __Known Data | Virtual Disk File Contents__:

![alt](images/inventory/app-2-binaries.png "App bundle client item with two binaries")

Create a filter via __Manage Application__ for all binaries listed and add all of those filters to a policy to correctly handle the .app bundle.

## App Bundle Contents Info.plist (binary format)

Depending on how the vendor created the .app bundle, the level of detail to be inventoried might vary. Sometimes it is necessary to look at other artifacts in the bundle to customize the filter and or policy further.

For this we will look at an Info.plist file in binary format. For example,

* to manually add a Bundle Identifier to the filter, search for the tag `<CFBundleIdentifier>` and enter the string value in the appropriate filter field.
* to manually add a Bundle Version (short) to the filter, search for the tag `<CFBundleShortVersionString`> and enter the string value in the appropriate filter field.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>BuildMachineOSBuild</key>
	<string>19G2021</string>
	<key>CFBundleDevelopmentRegion</key>
	<string>en</string>
	<key>CFBundleDisplayName</key>
	<string>Avast</string>
	<key>CFBundleDocumentTypes</key>
	<array>
		<dict>
			<key>CFBundleTypeName</key>
			<string>Any Item</string>
			<key>CFBundleTypeRole</key>
			<string>None</string>
			<key>LSHandlerRank</key>
			<string>None</string>
			<key>LSItemContentTypes</key>
			<array>
				<string>public.item</string>
			</array>
		</dict>
	</array>
	<key>CFBundleExecutable</key>
	<string>Avast</string>
	<key>CFBundleIconFile</key>
	<string>AppIcon</string>
	<key>CFBundleIdentifier</key>
	<string>com.avast.AAFM</string>
	<key>CFBundleInfoDictionaryVersion</key>
	<string>6.0</string>
	<key>CFBundleName</key>
	<string>Avast</string>
	<key>CFBundlePackageType</key>
	<string>APPL</string>
	<key>CFBundleShortVersionString</key>
	<string>14.9</string>
	<key>CFBundleSupportedPlatforms</key>
	<array>
		<string>MacOSX</string>
	</array>
	<key>CFBundleURLTypes</key>
	<array>
		<dict>
			<key>CFBundleTypeRole</key>
			<string>Viewer</string>
			<key>CFBundleURLName</key>
			<string>com.avast.webdocument</string>
			<key>CFBundleURLSchemes</key>
			<array>
				<string>avastav</string>
			</array>
		</dict>
	</array>
	<key>CFBundleVersion</key>
	<string>1</string>
	<key>DTCompiler</key>
	<string>com.apple.compilers.llvm.clang.1_0</string>
	<key>DTPlatformBuild</key>
	<string>12B45b</string>
	<key>DTPlatformName</key>
	<string>macosx</string>
	<key>DTPlatformVersion</key>
	<string>11.0</string>
	<key>DTSDKBuild</key>
	<string>20A2408</string>
	<key>DTSDKName</key>
	<string>macosx11.0</string>
	<key>DTXcode</key>
	<string>1220</string>
	<key>DTXcodeBuild</key>
	<string>12B45b</string>
	<key>LSMinimumSystemVersion</key>
	<string>10.10</string>
	<key>LSUIElement</key>
	<true/>
	<key>NSCameraUsageDescription</key>
	<string>Change Avast Omni profile picture</string>
	<key>NSHumanReadableCopyright</key>
	<string>Copyright © 2021 AVAST Software s.r.o. All rights reserved.</string>
	<key>NSMainNibFile</key>
	<string>MainMenu</string>
	<key>NSPrincipalClass</key>
	<string>Avast.AntivirusModule</string>
	<key>NSServices</key>
	<array>
		<dict>
			<key>NSMenuItem</key>
			<dict>
				<key>default</key>
				<string>Scan with Avast</string>
			</dict>
			<key>NSMessage</key>
			<string>scanFromServicesMenu</string>
			<key>NSPortName</key>
			<string>Avast</string>
			<key>NSRequiredContext</key>
			<dict>
				<key>NSApplicationIdentifier</key>
				<string>com.apple.finder</string>
			</dict>
			<key>NSSendFileTypes</key>
			<array>
				<string>public.item</string>
			</array>
			<key>NSServiceDescription</key>
			<string>ScanServicesDesc</string>
		</dict>
	</array>
</dict>
</plist>
```
