[title]: # (Message Localization)
[tags]: # (overview)
[priority]: # (10)
# Action Message Localization

Action messages can be localized for user interaction on endpoints. For this to work, create a duplicate the __Approval Request Form Action__ and then view and modify the XML of that duplicated item.

If you look at the xml example code below, you will the `<axc:LocaleResourceCollection x:Key="LocaleResources">` element with one child `<axc:LocaleResourceSet>`. This child is the default language for the approval request, which is English.

To add a localization such as Spanish:

1. Copy the `<axc:LocaleResourceSet>` element block including the `</ axc:LocaleResourceSet>` element.
1. Paste it underneath `</ axc:LocaleResourceSet>`.
1. Add `Language="es"`, as in `<axc:LocaleResourceSet Language="es">`.
1. Modify the elements with string values to the correct translation for that language.

For a list of valid language code values, refer to https://docs.microsoft.com/en-us/openspecs/office_standards/ms-oe376/6c085406-a698-4e12-9d4d-c3b0ee3dbc4a (the more specific language is used first, such as ‘es-ES' for Spanish – Spain and then the broader ‘es' will be used if a specific language translation is not found, the last resort is the invariant translation).

## Example for Spanish

Open this [link](scripts/spanish.xml) to access, copy, or download the example xml.
