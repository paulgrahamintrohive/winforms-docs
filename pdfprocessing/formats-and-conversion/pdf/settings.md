---
title: Settings
page_title: Settings | UI for WinForms Documentation
description: Settings
slug: winforms/pdfprocessing/formats-and-conversion/pdf/settings
tags: settings
published: True
position: 3
previous_url: pdfprocessing-formats-and-conversion-pdf-settings
---

# Settings

__PdfFormatProvider__ provides you with the ability to import/export PDF documents. Additionally, you can take advantage of the import/export settings that give you modification options.

## Import Settings

You can specify the import settings you wish through the __ImportSettings__ property of __PdfFormatProvider__.The available import settings are these:

__UserPasswordNeeded__

The event is fired when a user password is needed to open the document. The password can be specified in the __PasswordNeededEventArgs.Password__ property.

__Example 1__ shows how you can create a __PdfImportSettings__ object and assign it to a PdfFormatProvider.

#### Example 1: Import Settings

#### Example 1: Import Settings Event Handler

{{source=..\SamplesCS\PdfProcessing\Formats and Conversion\Pdf\PdfProcessingFormatsAndConversionPdfSettings.cs region=radpdfprocessing-formats-and-conversion-pdf-settings_0}}
{{source=..\SamplesVB\PdfProcessing\Formats and Conversion\Pdf\PdfProcessingFormatsAndConversionPdfSettings.vb region=radpdfprocessing-formats-and-conversion-pdf-settings_0}}

````C#
PdfFormatProvider provider = new PdfFormatProvider();
PdfImportSettings settings = new PdfImportSettings();
settings.UserPasswordNeeded += new EventHandler<PasswordNeededEventArgs>(settings_UserPasswordNeeded);
provider.ImportSettings = settings;

````
````VB.NET
andler
    Private Sub UserPasswordNeeded_EventHandler(sender As Object, e As PasswordNeededEventArgs)
        e.Password = "D0cum3ntP4ssw0rd"
    End Sub

````

{{endregion}}

{{source=..\SamplesCS\PdfProcessing\Formats and Conversion\Pdf\PdfProcessingFormatsAndConversionPdfSettings.cs region=radpdfprocessing-formats-and-conversion-pdf-settings_0Handler}} 
{{source=..\SamplesVB\PdfProcessing\Formats and Conversion\Pdf\PdfProcessingFormatsAndConversionPdfSettings.vb region=radpdfprocessing-formats-and-conversion-pdf-settings_0Handler}}

````C#
private void settings_UserPasswordNeeded(object sender, PasswordNeededEventArgs e)
{
    e.Password = "D0cum3ntP4ssw0rd";
}

````
````VB.NET
Private Sub UserPasswordNeeded_EventHandler(sender As Object, e As PasswordNeededEventArgs)
    e.Password = "D0cum3ntP4ssw0rd"
End Sub

````

{{endregion}}

## Export Settings

In order to modify the way content is exported you can set the __ExportSettings__ property of __PdfFormatProvider__. These are the modification options you can use:
        

__IsEncrypted__

This property specifies if the document should be encrypted. The default value is False.
        

>note This setting is ignored when __ComplianceLevel__ differs from None as PDF/A compliant documents do not allow encryption.
>


__UserPassword__

The password to be used if the document is encrypted. The default password is empty string.
        

__ImageQuality__

The ImageQuality property specifies the quality with which images are exported to PDF. More information about how it works is available in [this article]({%slug radpdfprocessing-concepts-imagequality%}).
        

__ComplianceLevel__

Specifies the PDF/A compliance level. It can have one of the following values:        
        

* __None__: Specify no compliance level.
            

* __PdfA1B__: Specify PDF/A-1b compliance level.
            

* __PdfA2B__: Specify PDF/A-2b compliance level.
            

* __PdfA2U__: Specify PDF/A-2u compliance level.
            

* __PdfA3B__: Specify PDF/A-3b compliance level.
            

* __PdfA3U__: Specify PDF/A-3u compliance level.
            

The default value is *None*. For more information on PDF/A compliance check the PDF/A Compliance article.

__Example 2__ shows ow you can create a __PdfExportSettings__ object and assign it to a PdfFormatProvider.

#### Example 2: Export Settings


{{source=..\SamplesCS\PdfProcessing\Formats and Conversion\Pdf\PdfProcessingFormatsAndConversionPdfSettings.cs region=radpdfprocessing-formats-and-conversion-pdf-settings_1}} 
{{source=..\SamplesVB\PdfProcessing\Formats and Conversion\Pdf\PdfProcessingFormatsAndConversionPdfSettings.vb region=radpdfprocessing-formats-and-conversion-pdf-settings_1}} 

````C#
PdfFormatProvider provider = new PdfFormatProvider();
PdfExportSettings settings = new PdfExportSettings();
settings.IsEncrypted = true;
settings.UserPassword = "D0cum3ntP4ssw0rd";          
settings.ComplianceLevel = PdfComplianceLevel.PdfA2B;
provider.ExportSettings = settings;

````
````VB.NET
Dim provider As PdfFormatProvider = New PdfFormatProvider()
Dim settings As PdfExportSettings = New PdfExportSettings()
settings.IsEncrypted = True
settings.UserPassword = "D0cum3ntP4ssw0rd"     
settings.ComplianceLevel = PdfComplianceLevel.PdfA2B
provider.ExportSettings = settings

````

{{endregion}} 

# See Also

 * [How to Comply with PDF/A Standard]({%slug winforms/pdfprocessing/how-to/how-to-comply-with-pdf/a-standard%})
