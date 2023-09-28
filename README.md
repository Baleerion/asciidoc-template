# AsciiDoc Template

## Instructions for use

It is recommended to create a Git repository for each document to be generated. 
You can generate several documents in the same repository, but it's easy to get 
lost as the documents are split into sub-parts.

## Prerequisites

A text editor with modules to make writing and viewing AsciiDoc easier 
(VSCode/VSCodium, for instance)

For **Windows** :
- WSL2
- Docker or Podman

For **Linux** :
- Docker or Podman

For **MAC** : untested

## Structure

Repository structure :
- **addons** : additional modules. There is a module for creating a table of 
images and another for creating fillable fields.
- **content** : Contents of the document. Documents can be divided into 
sub-sections and these sub-sections can be included in the main document.
- **fonts** : fonts and their variations. 
- **images** : images used for the document.
- **locale** : translation files.
- **styles** : files for the PDF theme. The file you need to override is 
theme-name.yml
- **vars** : files that contain variables used in the document and for PDF 
generation
- **.env** : file containing 3 environment variables, one for the language, 
another for the image of the container to be used and the third for the name of 
the main file.
- **generate-pdf** : bash script to generate the PDF.
- a file **.adoc** : main file. The name of this file may change.

## PDF generation

2 ways :
- With the `generate-pdf` script
- Use a continuous integration pipeline and retrieve the files from the 
platform used.

The options available for the `generate-pdf` script :
- -l or --lang : Language name in 'xx_XX' format.
- -f or --name : Name of the input document. The default name is document.adoc.
- -o : Name of the output document. By default, the name will be that of the 
subject and the version.
- -a or --adoc : Generate using the local asciidoctor-pdf software
- -p or --podman : Generate using Podman
- -d or --docker : Generate using Docker
- -h or --help : Display the help message

## Additional documentation

General documentation for syntax in AsciiDoc : https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/

Basic documentation for "Asciidoctor PDF", the project that generates PDFs from .adoc files : https://docs.asciidoctor.org/pdf-converter/latest/

## Coming soon

Compatibility with nerdctl and containerd

