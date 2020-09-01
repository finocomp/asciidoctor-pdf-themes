# Asciidoctor PDF Themes

Themes for the [AsciidoctorPdf plugin](https://asciidoctor.github.io/asciidoctor-gradle-plugin/development-3.x/user-guide/#asciidoctorj-pdf-plugin) to be used in generated PDFs.

## Using the Themes
The documentation for the plugin should be your primary source on its usage, however some of that information is duplicated here.

Add the plugin to your `build.gradle` (version subject to change):
```groovy
plugins {
    id 'org.asciidoctor.jvm.pdf' version '3.1.0'
}
```

When applying `org.asciidoctor.jvm.pdf` it creates a single task of type `org.asciidoctor.gradle.jvm.pdf.AsciidoctorPdfTask` an extension called `pdfThemes`.

The plugin supports loading a PDF theme from an external repository (this one ideally):
```groovy
pdfThemes {
    github 'finocomp', { 
        organisation = 'finocomp' 
        repository = 'asciidoctor-pdf-themes' 
        relativePath = 'themes/finocomp' 

        // one of the following
        branch = 'master' 
        tag = '1.0.1' 
        commit = '4910271e8c3964b60e186a62f3e4339ed0752714' 
    }
}
```

If you want to use more than one theme, then the block will need to be repeated for each theme and the name and relativePath adjusted accordingly. Gradle will however, only download the repository once.

## Customising Themes

Documentation on Asciidoctor PDF Themes can be found [here](https://github.com/asciidoctor/asciidoctor-pdf/blob/master/docs/theming-guide.adoc).