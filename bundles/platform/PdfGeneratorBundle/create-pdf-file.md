<a id="bundle-docs-platform-pdf-generator-bundle-create-pdf-file"></a>

# Create a PDF File

The overall chain of generating a `PDF file` is as follows:

```none
``Start`` -> ``PDF builder factory`` -> Create ``PDF builder`` -> ``PDF builder`` -> Create ``PDF file`` -> ``PDF engine`` -> Create ``PDF file`` -> ``PDF file`` -> ``End``
```

Example:

```php
$pdfBuilder = $this->pdfBuilderFactory->createPdfBuilder(PdfOptionsPreset::DEFAULT_PRESET);
$pdfTemplate = $this->pdfTemplateFactory->createPdfTemplate(
    '@AcmeDemo/PdfDocument/template.html.twig',
    ['param1' => 'value1', 'param2' => 'value2']
);
$pdfBuilder->content($pdfTemplate);
// Set the page size to A4 format width and height.
$pdfBuilder->setPageWidth('8.27in');
$pdfBuilder->setPageHeight('11.7in');
/* @var $pdfFile \Oro\Bundle\PdfGeneratorBundle\Model\PdfFileInterface */
$pdfFile = $pdfBuilder->createPdfFile();
```
