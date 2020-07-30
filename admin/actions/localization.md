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

For a list of valid language code values, refer to https://docs.microsoft.com/en-us/openspecs/office_standards/ms-oe376/6c085406-a698-4e12-9d4d-c3b0ee3dbc4a (the more specific language is used first, such as ‘es-ES’ for Spanish – Spain and then the broader ‘es’ will be used if a specific language translation is not found, the last resort is the invariant translation).

## Example for Spanish

```xml
<CustomXamlExecutionActionContract xmlns:adc="http://schemas.arellia.com/dc/" xmlns:arr="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:mss="http://schemas.microsoft.com/2003/10/Serialization/" xmlns:dc="http://schemas.datacontract.org/2004/07/System" xmlns:d1p4="http://schemas.arellia.com/dc/ClientItem/" xmlns:d1p5="http://schemas.arellia.com/dc/ApplicationControl/ApplicationActions/" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.arellia.com/dc/ApplicationControl/ApplicationAction/">
    <adc:Attributes>NoReplication System</adc:Attributes>
    <adc:Description>This action will display a approval request form for approval before allowing application to run.</adc:Description>
    <adc:FolderId>cf02777a-86b3-4450-b5af-1dcbee252071</adc:FolderId>
    <adc:ItemId>5d4e0cb0-604b-4fc4-968c-e68a8b5c7838</adc:ItemId>
    <adc:Name>Approval Request Form Action (with Localization)</adc:Name>
    <adc:ProductId>27bedb8a-db37-4d53-b748-bc6651461fe4</adc:ProductId>
    <adc:Strings />
    <adc:Tags />
    <AdjustSession>false</AdjustSession>
    <Commandline>/approvalTypeId:2A3F33C4-15DD-41D0-A620-889EA1E4408A</Commandline>
    <Executable>.\ArelliaDisplayXamlAction.exe</Executable>
    <TerminateExitCode>1</TerminateExitCode>
    <WaitOnApplication>true</WaitOnApplication>
    <ChildAssociations />
    <OfflineApprovalType>OfflineNotAllowed</OfflineApprovalType>
    <OwnsItemIds />
    <RequireLogon>false</RequireLogon>
    <UserGroupId i:nil="true" />
    <Xaml><![CDATA[<Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib"
        xmlns:adx="http://schemas.arellia.com/winfx/2012/arelliadisplayxamlaction"
        xmlns:ac="http://schemas.arellia.com/winfx/2010/xaml"
        xmlns:acs="http://schemas.arellia.com/silverlight/2012/acs"
        xmlns:axc="http://schemas.arellia.com/xaml/2014/xaml/common"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="ac acs"
        Icon="Images/thycotic-icon.png"
        WindowStartupLocation="CenterScreen"
        ResizeMode="NoResize"
        SizeToContent="WidthAndHeight"
        Topmost="True">
        <Window.Resources>
            <axc:LocaleResourceCollection x:Key="LocaleResources">
                <axc:LocaleResourceSet>
                    <axc:StringKeyedResource Key="ApplicationTitle" Value="Application Notice" />
                    <axc:StringKeyedResource Key="UserLabel" Value="User:" />
                    <axc:StringKeyedResource Key="ApplicationLabel" Value="Application:" />
                    <axc:StringKeyedResource Key="ReasonLabel" Value="Reason (required):" />
                        <axc:StringKeyedResource Key="InformationTextSection">
                            <axc:StringKeyedResource.Value>
                                <Section xml:space="preserve">
                                    <Paragraph><Run>This application has </Run><Bold><Run>not been approved</Run></Bold><Run> for use according to corporate policy. Please discontinue use or enter your justification to continue.</Run></Paragraph>
                                </Section>
                            </axc:StringKeyedResource.Value>
                        </axc:StringKeyedResource>
                        <axc:StringKeyedResource Key="InstructionTextSection">
                            <axc:StringKeyedResource.Value>
                                <Section xml:space="preserve">
                                    <Paragraph><Run>Type a brief explanation describing why this application is necessary. This explanation will form part of the request and will be reviewed by IT staff in consideration of this request.</Run></Paragraph>
                                </Section>
                            </axc:StringKeyedResource.Value>
                        </axc:StringKeyedResource>
                        <axc:StringKeyedResource Key="ContinueButtonLabel" Value="Continue" />
                        <axc:StringKeyedResource Key="CancelButtonLabel" Value="Cancel" />
                        <axc:StringKeyedResource Key="RefreshButtonLabel" Value="Refresh" />
                        <axc:StringKeyedResource Key="TitlePrefix" Value="Application Notice" />
                        <axc:StringKeyedResource Key="FlowDirection" Value="LeftToRight" />
                        <axc:StringKeyedResource Key="DefaultFontSize" Value="11" />
                        <axc:StringKeyedResource Key="ApprovalStatusLabel" Value="Approval status:" />
                        <axc:StringKeyedResource Key="ApprovalStatusTextSection">
                            <axc:StringKeyedResource.Value>
                                <Section xml:space="preserve">
                                    <Paragraph><Run>A previous request for this application has been submitted for review.</Run></Paragraph>
                                </Section>
                            </axc:StringKeyedResource.Value>
                        </axc:StringKeyedResource>
                </axc:LocaleResourceSet>
                <axc:LocaleResourceSet Language="es">
                    <axc:StringKeyedResource Key="ApplicationTitle" Value="Aviso de solicitud" />
                    <axc:StringKeyedResource Key="UserLabel" Value="El Consumidor:" />
                    <axc:StringKeyedResource Key="ApplicationLabel" Value="Solicitud:" />
                    <axc:StringKeyedResource Key="ReasonLabel" Value="Motivo (requerido):" />
                    <axc:StringKeyedResource Key="InformationTextSection">
                        <axc:StringKeyedResource.Value>
                            <Section xml:space="preserve">
                                <Paragraph><Run>Esta solicitud no ha sido aprobada para su uso de acuerdo con la política corporativa. Deje de usar o ingrese su justificación para continuar.</Run></Paragraph>
                            </Section>
                        </axc:StringKeyedResource.Value>
                    </axc:StringKeyedResource>
                    <axc:StringKeyedResource Key="InstructionTextSection">
                        <axc:StringKeyedResource.Value>
                            <Section xml:space="preserve">
                                <Paragraph><Run>Escriba una breve explicación que describa por qué es necesaria esta aplicación. Esta explicación formará parte de la solicitud y será revisada por el personal de IT en consideración de esta solicitud.</Run></Paragraph>
                            </Section>
                        </axc:StringKeyedResource.Value>
                    </axc:StringKeyedResource>
                        <axc:StringKeyedResource Key="ContinueButtonLabel" Value="Seguir" />
                        <axc:StringKeyedResource Key="CancelButtonLabel" Value="Cancelar" />
                        <axc:StringKeyedResource Key="RefreshButtonLabel" Value="Recargar" />
                        <axc:StringKeyedResource Key="TitlePrefix" Value="Aviso de solicitud" />
                        <axc:StringKeyedResource Key="FlowDirection" Value="LeftToRight" />
                        <axc:StringKeyedResource Key="DefaultFontSize" Value="11" />
                        <axc:StringKeyedResource Key="ApprovalStatusLabel" Value="Estado de aprobación:" />
                    <axc:StringKeyedResource Key="ApprovalStatusTextSection">
                        <axc:StringKeyedResource.Value>
                            <Section xml:space="preserve">
                                <Paragraph><Run>Se ha enviado una solicitud previa para esta solicitud para su revisión.</Run></Paragraph>
                            </Section>
                        </axc:StringKeyedResource.Value>
                    </axc:StringKeyedResource>
                </axc:LocaleResourceSet>
            </axc:LocaleResourceCollection>
            <!-- common control styles -->
                <Style x:Key="BaseLabelStyle" TargetType="TextBlock">
                    <Setter Property="Margin" Value="10,3" />
                </Style>
                <Style x:Key="BaseButtonStyle" TargetType="Button">
                    <Setter Property="Padding" Value="15,3" />
                    <Setter Property="MinHeight" Value="25" />
                    <Setter Property="MinWidth" Value="85" />
                </Style>
                <Style x:Key="ReadOnlyFieldStyle" TargetType="TextBlock">
                    <Setter Property="FontWeight" Value="Bold" />
                    <Setter Property="VerticalAlignment" Value="Center" />
                    <Setter Property="TextWrapping" Value="Wrap" />
                </Style>
                <Style x:Key="BaseRichTextBoxStyle" TargetType="RichTextBox">
                    <Setter Property="BorderThickness" Value="0" />
                    <Setter Property="Background" Value="Transparent" />
                    <Setter Property="Padding" Value="0" />
                    <Setter Property="IsReadOnly" Value="True" />
                    <Setter Property="IsTabStop" Value="False" />
                </Style>
            <!-- specific element styles -->
                <axc:StringFormatter x:Key="WindowTitle" FormatString="{}{0}: {1}">
                    <axc:StringFormatter.Parameter0>
                        <Binding Path="[TitlePrefix]" Source="{StaticResource LocaleResources}" />
                    </axc:StringFormatter.Parameter0>
                    <axc:StringFormatter.Parameter1>
                        <Binding Path="ProcessName" />
                    </axc:StringFormatter.Parameter1>
                </axc:StringFormatter>
                <sys:String x:Key="EncodedLogoImage">iVBORw0KGgoAAAANSUhEUgAAAQcAAABYCAIAAAB3ZqVmAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAA4rSURBVHhe7ZxfjBXVHcf3TwGVrn+q1aZt2qemSdO+tE2K3Lkzdy9uKa0mdgmyiWnaCAWyRRqguIu77sJSML6YWDEFdS1GMLSWCorILktD6IvGNxNeqD6QGEhMSHwgPuCf9jdzvvcyZ+b85s6Zmbtc7v19cnJz7/l953fnzJzvnDN/7u0qC4KgI64QhCjiCkGIIq4QhCjiCkGIIq4QhChpXeG6Lt7Z4zgO3sXIk1bIRsLuUMhOSeUK2kyZt1TyPsiTWWgGtDsa2iZOm+1EixnU/xKByMRLL70EkYlHHnkEOmEewdZngEgHMYYrV65Ad+MjruhQsPUZINJBjEFcYQAiE+KKFgRbnwEiHcQYxBUGIDIhrmhBsPUZINJBjEFcYQAiE+KKFgRbnwEinf8kMjc3B92Nj7iiQ8HWZ4CoU0nrCtd1scFMfPnll9CZsHVF5Mqg+tiMq+wZLkHGUd8b/vZw2iZdssyw5pFFsPUZINJJbkv6VUq/TQrZQRlIcsXbNU6cOEGv2GAMSqk4efLk/fffjywpXPHCCy/gQ2AwvNN5//334/0vzH8Tefjhh6GLAUWM8+fP0ytEjXjxxRexojGoRQRtlmwO2b17dz2PepPAO++8g8V0qHs99dRTau8osAADRAEqA608pko8SsmhuvjatWs/+OADfE1ApF2ffPLJtm3b1LZqRVdgNTOxatUqZGnkClsefPBByhnvYQgzJMzToGCAyMTg4CBEloyMjKj153xC9dQhoM5EvL3UvxGzBMun6A/Q6VBDqDmffvopRDZ89tlnKoNKNW/ceK4g1q1bh9QhEGMo3BUI52BgYAC5YqxZswaifCBdwHVxBXXoM2fOIJyVq1evcoePJsG6gtYDK5Vi7I4LmuoKAqlDIMBQlCvUcSvNZCYN27dvV2nDhLd8AuF14NaH6imhWuewK6zWP1gpH3zmga4GNeTjjz9GLDdIOi+wrqBNSb25zvT0NNaOAboaK1asQKIUroAuQB0V9uzZgxhD/OCBAENRrqDvTe5STz75pJIp/TPPPIMAA2nqMwT1BgEG0kTafvnyZcRM0DRPycbGxtSuoV3ZcI8opUItTiDGA12NarVKlQmbS8moOQrUMly4cEHp54GkGVQErB0DRCZoy0LEAJ0OnR0ibAKiEAgwFOKKhr2W+oFSRkDYxNTUFEQBy5cvR8AEdR3oQtBaIWxCTc3jIMwAkQ5iPNDVQC0DRDVU0xBjUMp5oHVdkbyzIQqBAENRYwVqGSCKkXC8jFy6QS0DRDEQZoBIBzEGiHQQ44EuoOGxHzodmngjHEPNBueH1nUFgbAJKEIgwHB9XYGwibArsvUkAmEGiHQQY4BIBzEe6IKGjI6OopYBUp0EVxAQNR9xhV27UMsAUQyETbTrWHHx4kXUMkCnI664BnQxEDYBRQgEGApxRTOO5e3qClTxQKdDruBmmzKDAgibgCIEAgwyVkRAjAEiHcR4lCzNeTOhxBFkrLgGdDEQNgFFCAQYrq8r0oNEDBDFQJgBIh3EGCDSQYwHugBU8UDXkogr7NqFWgaIcoBEDBDFQJgBIh3EGCDSQYwHugBU8UDXkogr7NqFWgaIcoBEDBDFQJgBIh3EGCDSQYwHugBU8UDXkogr7NqFWgaIcoBEDBDFQJgBIh3EGCDSQYwHugBU8UDXkogr7NqFWgaIcoBEDBDFQJgBIh3EGCDSQYwHugBU8UDXkogr7NqFWgaIcoBEDBDFQJgBIh3EGCDSQYwHugBU8UDXkogr7NqFWgaIcoBEDBDFQJgBIh3EGCDSQYwHugBU8UDXkogr7NqFWgaIcoBEDBDFQJgBIh3EGCDSQYwHugBU8UDXkogr7NqFWgaIcoBEDBDFQJgBIh3EGCDSQYwHugBU8UDXkogr7NqFWgaIcoBEDBDFQJgBIh3EGCDSQYwHugBU8UDXkogr7NqFWgaIcpDwzDkBUQyEGSDSQYwBIh3EeKALQBUPdDpuAD6koOKUvbKFXuHiV14s4gq7dqGWAaIYCJuQpwPD2D8HVZo41bXDunRTQQIT4gq7dqGWAaIYCJtoy99XEKjigU7H3hUeHfipi+861RPr+g0KEpgQV9i1C7UMEMVA2ES7jhUffvghahmg07F1BR1HnGACNTUb7fQNS5DAjLjCrl2oZVA/7I6DsAlyRXgmjVoGbs6NMANEOogxQKSDGA90AevXr0ctA3Q11KZLcEXi7yvUiNFl5Q0saqIjXEEbdNOmTdDFgIgBohpffPEFAiYgioGwibNnz4b7evLBMoMraIUh0kGYASIdxHigq4FaBuMRxH4G5aNGDMdxI/0+uWBhE50yVpAxVq9eDWmI5F5OQBcCARObN2+GKATtM4RNbNiwAbqA5P9wICgbAXWQ/KOPPkLMxNDQEKQ6CDNApIMYD3Q1UMsAkQ5iDBDFcMslOu2mNxNv0ml0tPdzRS1rpINcgXeWIHsIBEzQt3z++efhXmvluqDDu8l/flMnTYtIg9QxoGCASAcxHugC1EZAgGFiYqIu3r9/P2oZDhw4oMRx6FDiOv073+6WGVSUwcHBzF0/AWTXQSw3/f39yKjT8A8yGqI2BdKZUDIOiHQQ44EuxL59+xCzJ7I3kTFGcPOhtHNGrkExiwwPDyNcHEito+Y5OU2IXAz1qVS2bzl8+LBKorLFgY4BIh3EeKDTWblyJYXybKuZmRnkMlCicWLnDPVyi7mTKkhgoq1coaAOAVERICnDlStXoLMBC6ej4X9yhrl8+TIWawQWYIBIBzEG6vfQmRgZGVEaJU4J9RwsH4OGCP+/RWmUmIt295QFiUxYuCIban7JQVHueJZwnCMSohQi1PfSa7Vafeihh1atWqX++lbVK42vzuH2egaC3u/Zs+fcuXNYLAQ55+DBg5VKJay3hZattyghT56vUFCGDEkaLlLf7PS6evXqY8eOXb16lTZO3SfqzbvvvrtlyxYlJupvTJQct5zZElSQxkTTXdEiJOw2tVc4IBJaCP9yE71GerltCZKY6QhXJB/J0P0ZIBJaBrU3aZSYmrU+lwgXlc1I+7gCvZihqHvbwnWEziVoTuU63o7T0S6eVGZ7p2a7dvlzLc1FSGpCXCGuuGEgP5AxJv1Rojfcv5PLLno93bXxuTsiYwuSmhBXiCsi+D0vA8EN5mZBydVaWY0SO+d6gtPx7scOLfaTOB4NGsFlXL/46RjaxxXJV/3WrFkDnQ5NUqGIoRJC1zF45Uq5lMUW2byUHpo5UVe2GiWoTMz2jB9ZSMv6GRzPK197VkqlNdIpY8Xx48eh87cvLnGqj1CY4B6ta2+WLb/3z3Pd6kCbsuzwxT00yviXSwslGII8KvXenKbQKtGw4D8A8lbk10UeJfRHjDlxRcDevXvrTqhflUKMoa7vHIKjqveLlT+p9/g0hSY29Dp1ulsdlYuF+nGGW9e7TvXQicTS6A70/JGw5E7MdoYrCPTlgnjvvfeQt/Nwyt6v1/4w3O/TFDViVMpLnLL5+S5L/CdhaU0i3T25BD/KUxZK+g1qMu3jCo8mjTVj2D5ZEOfSpUsqbWcSDJLeb8e/qwaBlEWJd811VfoLOPP2/6ggy6063xK0DmUnuzPbaqyog66dlUqlgkQdz8bn7vT7+r+13p+i9FQ8/zCPLPbQmbHtKBGU7sngohOyZKUNXUHnDOq0gV6NDyZxTE9PqwxCjVKp7Gx/dbHViEGWoBMM6qOZRwx1HZZS1eZCKYsvpqVonZEoK+05VggFQh10/OiCSTtjoJv2V+n4ZDVilFzXH6jJh6Hu3qCQCXE6MdejsuREXCE0ouQ/ruvfIQ6OxFaFFvGq9yJPGsgU5dKk/0821zp9w0LihhdbrRBXCKmoPbbdvcO/j0ZzlbRl8tRXqtWlyMLjlPtd/z8JSlajROC94Fd4p4vsyeIKIRX+n2i4pfGZnomT3RMn6dWuVJYtQSIGmjg5jkud2+r/zsgSk8EoUextEnGFYAF5Y+zEwidOLLAq4yd6xt9aWF1WchzjoOHR+XGmW3W+nqZPSFMc4grBCv/O2tjxBRNvLBp7M3U5vmDszZsef2Nh/33IoqMuwnbvmrFyBWZoyFEo4gohA972YzeNHb1l9OiCsaP0Jm15/PVFywZ+5pRwO8j1b7T5DybRLCjW6RsUdTqu8hSOuEKwxqXzYsd97MjNo69/dfuRW1KW0X/ePHpk0ci/bqr+vH6O4V07idc7fcOyc6aJXVdcIWTEK7sjry2msu21PvUmZXnsH7dUyBgenV/7j69GunvKgpVoDuIKIQeeu/XvfdsOU1mcukA8sGIJHvaO9fjkQovkeZYkDeIKIReuU95ysG/rq31/OtS39dCtjcurfUof3PeI9vjk4v/EdLZ3Hh7vF1cI+XArnutsfuXWLQdvo9d05fbarcBov08udIZdHSj+9xtxxBVCAdCI8ccDd9TK7VzZ9LfbHn359izn1sE97BUP/Bjf12TEFUIheGVv6aPTd26aviOhkIAsEVx0siyzvb8a+pH/Pa7NU1VZEVcIhdF/X2n4+a9tfP4uU7l7eP/XM4wSwWN/PUMbvu8bb74QVwhFMvDAkuG/3u2XfXddK/Rx/z0ZR4lTXb8Z/05gCXGFcMPyy6GfDu/9xoZ6ec53RQY/TJ7qnZrt/cPTdztuAb93tUJcIRSM45YHN/xg3V/uobL+2W+uf/aebHevJ+e6tr7cR5bI+LdtORBXCE1haNv31j39rd8/SxOnaHdvWPxbe7O9jx9elP+3ptkQVwhNwS2Xfrf72+q/BdQ97PSFFnni7d5Seen8jxIKcYUgRBFXCEIUcYUgRBFXCEIUcYUgRBFXCEIUcYUgRBFXCIJOufx/rWQYFSQfyRYAAAAASUVORK5CYII=</sys:String>
            <!-- heading -->
                <Style x:Key="MainWindowPanelStyle" TargetType="Panel">
                    <Setter Property="Width" Value="500" />
                    <Setter Property="Background" Value="#FFF0F0F0" />
                </Style>
                <Style x:Key="HeadingBorderStyle" TargetType="Border">
                    <Setter Property="BorderThickness" Value="0,0,0,1" />
                    <Setter Property="BorderBrush" Value="#FF777777" />
                </Style>
                <Style x:Key="TitleHeadingBorderStyle" TargetType="Border">
                    <Setter Property="Grid.Column" Value="0" />
                    <Setter Property="Padding" Value="8" />
                    <Setter Property="Background" Value="Yellow" />
                </Style>
                <Style x:Key="TitleHeadingStyle" TargetType="TextBlock">
                    <Setter Property="Text" Value="{Binding [ApplicationTitle],Source={StaticResource LocaleResources}}" />
                    <Setter Property="FontSize" Value="16" />
                    <Setter Property="FontWeight" Value="Bold" />
                    <Setter Property="Foreground" Value="Black" />
                </Style>
                <Style x:Key="ImageHeadingBorderStyle" TargetType="Border">
                    <Setter Property="Grid.Column" Value="1" />
                    <Setter Property="Padding" Value="8" />
                    <Setter Property="Background" Value="#3d3d3d" />
                </Style>
                <Style x:Key="ImageHeadingStyle" TargetType="Image">
                    <Setter Property="Grid.Column" Value="1" />
                    <Setter Property="Height" Value="18" />
                    <Setter Property="FlowDirection" Value="{Binding [FlowDirection],Source={StaticResource LocaleResources}}" />
                </Style>
            <!-- content area -->
                <Style x:Key="ContentPanelStyle" TargetType="Panel">
                    <Setter Property="Margin" Value="8" />
                </Style>
                <Style x:Key="InformationRichTextBoxStyle" TargetType="RichTextBox" BasedOn="{StaticResource BaseRichTextBoxStyle}">
                    <Setter Property="Margin" Value="0,8,0,0" />
                </Style>
                <Style x:Key="PropertiesPanelStyle" TargetType="Panel">
                    <Setter Property="Margin" Value="0,8,0,0" />
                </Style>
                <Style x:Key="ApplicationNameLabelStyle" TargetType="TextBlock" BasedOn="{StaticResource BaseLabelStyle}">
                    <Setter Property="Grid.Row" Value="0" />
                    <Setter Property="Text" Value="{Binding [ApplicationLabel],Source={StaticResource LocaleResources}}" />
                </Style>
                <Style x:Key="ApplicationFieldStyle" TargetType="TextBlock" BasedOn="{StaticResource ReadOnlyFieldStyle}">
                    <Setter Property="Grid.Row" Value="0" />
                    <Setter Property="Grid.Column" Value="1" />
                    <Setter Property="Text" Value="{Binding ProcessName}" />
                </Style>
                <Style x:Key="UserNameLabelStyle" TargetType="TextBlock" BasedOn="{StaticResource BaseLabelStyle}">
                    <Setter Property="Grid.Row" Value="1" />
                    <Setter Property="Text" Value="{Binding [UserLabel],Source={StaticResource LocaleResources}}" />
                </Style>
                <Style x:Key="UserNameFieldStyle" TargetType="TextBlock" BasedOn="{StaticResource ReadOnlyFieldStyle}">
                    <Setter Property="Grid.Row" Value="1" />
                    <Setter Property="Grid.Column" Value="1" />
                    <Setter Property="Text" Value="{Binding UserName}" />
                </Style>
                <Style x:Key="ReasonSectionPanelStyle" TargetType="StackPanel">
                </Style>
                <Style x:Key="InstructionRichTextBoxStyle" TargetType="RichTextBox" BasedOn="{StaticResource BaseRichTextBoxStyle}">
                    <Setter Property="Margin" Value="0,8,0,0" />
                </Style>
                <Style x:Key="ReasonLabelStyle" TargetType="TextBlock">
                    <Setter Property="Text" Value="{Binding [ReasonLabel],Source={StaticResource LocaleResources}}" />
                    <Setter Property="Padding" Value="0,2" />
                    <Setter Property="Margin" Value="0,5,0,0" />
                    <Setter Property="FontWeight" Value="Bold" />
                </Style>
                <Style x:Key="ReasonTextBoxStyle" TargetType="TextBox">
                    <Setter Property="TabIndex" Value="1" />
                    <Setter Property="AcceptsReturn" Value="True" />
                    <Setter Property="Height" Value="64" />
                    <Setter Property="ScrollViewer.HorizontalScrollBarVisibility" Value="Disabled" />
                    <Setter Property="ScrollViewer.VerticalScrollBarVisibility" Value="Auto" />
                        <!-- Reason field in DataClass is limited to nvarchar(255); set maximum length accordingly -->
                    <Setter Property="MaxLength" Value="250" />
                    <Setter Property="TextWrapping" Value="Wrap" />
                    <Setter Property="Text" Value="{Binding ReasonText,Mode=TwoWay,UpdateSourceTrigger=PropertyChanged}" />
                </Style>
                <Style x:Key="GeneralErrorInfoStyle" TargetType="TextBlock">
                    <Setter Property="Margin" Value="5" />
                    <Setter Property="FontWeight" Value="Bold" />
                    <Setter Property="Foreground" Value="Red" />
                    <Setter Property="TextWrapping" Value="Wrap" />
                    <Setter Property="Text" Value="{Binding Error}" />
                    <Setter Property="Visibility" Value="Collapsed" />
                </Style>
            <!-- Approval Status -->
                <Style x:Key="ApprovalStatusSectionPanelStyle" TargetType="Grid">
                    <Setter Property="Visibility" Value="Collapsed" />
                </Style>
                <SolidColorBrush x:Key="ApprovedBackgroundBrush" Color="ForestGreen" />
                <SolidColorBrush x:Key="DeniedBackgroundBrush" Color="Red" />
                <SolidColorBrush x:Key="DefaultBackgroundBrush" Color="DimGray" />
                <adx:ApprovalStatusBrushProvider x:Key="ApprovalStatusBrushProvider"
                    ApprovedBrush="{StaticResource ApprovedBackgroundBrush}"
                    DeniedBrush="{StaticResource DeniedBackgroundBrush}"
                    DefaultBrush="{StaticResource DefaultBackgroundBrush}" />
                <Style x:Key="ApprovalStatusBorderStyle" TargetType="Border">
                    <Setter Property="Grid.Row" Value="1" />
                    <Setter Property="CornerRadius" Value="2" />
                    <Setter Property="Padding" Value="8,3" />
                </Style>
                <Style x:Key="ApprovalRequestStatusInformationRichTextBoxStyle" TargetType="RichTextBox" BasedOn="{StaticResource BaseRichTextBoxStyle}">
                    <Setter Property="Margin" Value="0,8" />
                    <Setter Property="Grid.ColumnSpan" Value="2" />
                </Style>
                <Style x:Key="ApprovalStatusLabelStyle" TargetType="TextBlock">
                    <Setter Property="Text" Value="{Binding [ApprovalStatusLabel],Source={StaticResource LocaleResources}}" />
                    <Setter Property="Foreground" Value="White" />
                    <Setter Property="Padding" Value="0,2" />
                    <Setter Property="Margin" Value="0,0,5,0" />
                </Style>
                <Style x:Key="ApprovalStatusFieldStyle" TargetType="TextBlock">
                    <Setter Property="Grid.Column" Value="1" />
                    <Setter Property="FontWeight" Value="Bold" />
                    <Setter Property="Foreground" Value="White" />
                    <Setter Property="Text" Value="{Binding ApprovalStatus}" />
                    <Setter Property="VerticalAlignment" Value="Center" />
                </Style>
                <Style x:Key="BottomActionPanelStyle" TargetType="Grid">
                    <Setter Property="Margin" Value="0,8,0,0" />
                </Style>
                <Style x:Key="ButtonPanelStyle" TargetType="StackPanel">
                    <Setter Property="Grid.Column" Value="1" />
                    <Setter Property="Orientation" Value="Horizontal" />
                    <Setter Property="HorizontalAlignment" Value="Right" />
                </Style>
                <Style x:Key="ContinueWithReasonButtonStyle" TargetType="Button" BasedOn="{StaticResource BaseButtonStyle}">
                    <Setter Property="Content" Value="{Binding [ContinueButtonLabel],Source={StaticResource LocaleResources}}" />
                    <Setter Property="Command" Value="{Binding ContinueWithReasonCommand}" />
                    <Setter Property="CommandParameter" Value="{Binding ReasonText}" />
                    <Setter Property="Margin" Value="8,0,0,0" />
                </Style>
                <Style x:Key="ContinueButtonStyle" TargetType="Button" BasedOn="{StaticResource BaseButtonStyle}">
                    <Setter Property="Content" Value="{Binding [ContinueButtonLabel],Source={StaticResource LocaleResources}}" />
                    <Setter Property="Command" Value="{Binding ContinueCommand}" />
                    <Setter Property="Margin" Value="8,0,0,0" />
                    <Setter Property="Visibility" Value="Collapsed" />
                </Style>
                <Style x:Key="RefreshButtonStyle" TargetType="Button" BasedOn="{StaticResource BaseButtonStyle}">
                    <Setter Property="Content" Value="{Binding [RefreshButtonLabel],Source={StaticResource LocaleResources}}" />
                    <Setter Property="Command" Value="{Binding RefreshApprovalCommand}" />
                    <Setter Property="Visibility" Value="Collapsed" />
                </Style>
                <Style x:Key="CloseButtonStyle" TargetType="Button" BasedOn="{StaticResource BaseButtonStyle}">
                    <Setter Property="Content" Value="{Binding [CancelButtonLabel],Source={StaticResource LocaleResources}}" />
                    <Setter Property="Command" Value="{Binding CloseCommand}" />
                    <Setter Property="Margin" Value="8,0,0,0" />
                </Style>
                </Window.Resources>
                <Window.FlowDirection>
                    <Binding Path="[FlowDirection]" Source="{StaticResource LocaleResources}" />
                </Window.FlowDirection>
                <Window.FontSize>
                    <Binding Path="[DefaultFontSize]" Source="{StaticResource LocaleResources}" />
                </Window.FontSize>
                <StackPanel Style="{StaticResource MainWindowPanelStyle}"
                    adx:WindowHelper.Title="{Binding Result,Source={StaticResource WindowTitle}}">
                        <Border Style="{StaticResource HeadingBorderStyle}">
                            <Grid>
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="*" />
                                    <ColumnDefinition Width="Auto" />
                                </Grid.ColumnDefinitions>
                        <Border Style="{StaticResource TitleHeadingBorderStyle}">
                            <TextBlock Style="{StaticResource TitleHeadingStyle}" />
                        </Border>
                        <Border Style="{StaticResource ImageHeadingBorderStyle}">
                            <Image Style="{StaticResource ImageHeadingStyle}" acs:ImageSourceHelper.EncodedImage="{StaticResource EncodedLogoImage}" adx:ImageSourceHelper.EncodedImage="{StaticResource EncodedLogoImage}" />
                        </Border>
                        </Grid>
                        </Border>
                <StackPanel Style="{StaticResource ContentPanelStyle}">
            <!-- Information of why this dialog needs attention -->
                <RichTextBox Style="{StaticResource InformationRichTextBoxStyle}"
                    ac:RichTextBoxHelper.Section="{Binding [InformationTextSection],Source={StaticResource LocaleResources}}"
                        adx:RichTextBoxHelper.Section="{Binding [InformationTextSection],Source={StaticResource LocaleResources}}" />
            <!-- Details about detected process -->
                <Grid Style="{StaticResource PropertiesPanelStyle}">
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="Auto" />
                        <ColumnDefinition Width="*" />
                    </Grid.ColumnDefinitions>
                    <Grid.RowDefinitions>
                        <RowDefinition />
                        <RowDefinition />
                    </Grid.RowDefinitions>
                    <TextBlock Style="{StaticResource ApplicationNameLabelStyle}" />
                    <TextBlock Style="{StaticResource ApplicationFieldStyle}" />
                    <TextBlock Style="{StaticResource UserNameLabelStyle}" />
                    <TextBlock Style="{StaticResource UserNameFieldStyle}" />
                </Grid>
                <StackPanel Style="{StaticResource ReasonSectionPanelStyle}"                     ac:VisibilityHelper.HiddenWhenTrue="{Binding IsPendingApproval}" adx:VisibilityHelper.HiddenWhenTrue="{Binding IsPendingApproval}">
            <!-- Instruction for Reason field -->
                <RichTextBox Style="{StaticResource InstructionRichTextBoxStyle}" ac:RichTextBoxHelper.Section="{Binding [InstructionTextSection],Source={StaticResource LocaleResources}}" adx:RichTextBoxHelper.Section="{Binding [InstructionTextSection],Source={StaticResource LocaleResources}}" />
            <!-- Reason field -->
                <TextBlock Style="{StaticResource ReasonLabelStyle}" />
                <TextBox Style="{StaticResource ReasonTextBoxStyle}" adx:FocusHelper.FocusOnLoaded="True" />
                </StackPanel>
                <Grid Style="{StaticResource ApprovalStatusSectionPanelStyle}" ac:VisibilityHelper.VisibleWhenTrue="{Binding IsPendingApproval}" adx:VisibilityHelper.VisibleWhenTrue="{Binding IsPendingApproval}">
                    <Grid.RowDefinitions>
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                    </Grid.RowDefinitions>
            <!-- Information for Approval Status -->
                    <RichTextBox Style="{StaticResource ApprovalRequestStatusInformationRichTextBoxStyle}"                         ac:RichTextBoxHelper.Section="{Binding [ApprovalStatusTextSection],Source={StaticResource LocaleResources}}"                         adx:RichTextBoxHelper.Section="{Binding [ApprovalStatusTextSection],Source={StaticResource LocaleResources}}" />
            <!-- Approval Status field -->
                    <Border Style="{StaticResource ApprovalStatusBorderStyle}" adx:ApprovalStatusBrush.Provider="{StaticResource ApprovalStatusBrushProvider}">
                        <Grid>
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="Auto" />
                                <ColumnDefinition Width="*" />
                            </Grid.ColumnDefinitions>
                        <TextBlock Style="{StaticResource ApprovalStatusLabelStyle}" />
                        <TextBlock Style="{StaticResource ApprovalStatusFieldStyle}" />
                        </Grid>
                    </Border>
                </Grid>
            <!-- Shows any general errors -->
                <TextBlock Style="{StaticResource GeneralErrorInfoStyle}" adx:VisibilityHelper.VisibleWhenPopulated="{Binding Error}" />
            <!-- Buttons at bottom -->
                <Grid Style="{StaticResource BottomActionPanelStyle}">
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="Auto" />
                        <ColumnDefinition Width="*" />
                    </Grid.ColumnDefinitions>
                    <Button Style="{StaticResource RefreshButtonStyle}" ac:VisibilityHelper.VisibleWhenTrue="{Binding IsPendingApproval}" adx:VisibilityHelper.VisibleWhenTrue="{Binding IsPendingApproval}" />
                    <StackPanel Style="{StaticResource ButtonPanelStyle}">
                    <Button Style="{StaticResource ContinueWithReasonButtonStyle}" ac:VisibilityHelper.HiddenWhenTrue="{Binding IsPendingApproval}" adx:VisibilityHelper.HiddenWhenTrue="{Binding IsPendingApproval}" adx:ButtonHelper.IsDefault="true" />
                    <Button Style="{StaticResource ContinueButtonStyle}" ac:VisibilityHelper.VisibleWhenTrue="{Binding IsRequestApproved}" adx:VisibilityHelper.VisibleWhenTrue="{Binding IsRequestApproved}" adx:ButtonHelper.IsDefault="true" />
                    <Button Style="{StaticResource CloseButtonStyle}" adx:ButtonHelper.IsCancel="true" />
                </StackPanel>
            </Grid>
        </StackPanel>
    </StackPanel>
    </Window>
]]></Xaml>
</CustomXamlExecutionActionContract>
```
