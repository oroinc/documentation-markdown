<a id="bundle-docs-commerce-frontend-pdf-generator-bundle"></a>

# OroFrontendPdfGeneratorBundle

OroFrontendPdfGeneratorBundle extends the PDF generation functionality provided by [OroPdfGeneratorBundle](../../platform/PdfGeneratorBundle/index.md#bundle-docs-platform-pdf-generator-bundle).

It provides the ability to generate and download `PDF documents` in the storefront; it declares the `oro_frontend_pdf_generator.pdf_document.url_generator` service that re-uses the existing `\Oro\Bundle\PdfGeneratorBundle\PdfDocument\UrlGenerator\PdfDocumentUrlGenerator` with the storefront route.
