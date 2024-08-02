# How to deploy IPv6 - a guide to Enterprises

## What is it?
This is a guide to deploy IPv6 in enterprises. It bases on the great work of Jean ... and ARCEP, you can find the original source here: ??

I decided to convert the pdf/docx to ASCIIDOC and host it on Github, because of much easier maintance, even with a lot help from the community. Help is very welcome!

Most documents on IPv6 are more than 10 years old, outdated and not helpful because of that. 

*I believe, that a good document about IPv6 is crucial for most IPv6 projects and we can only hold this document updated as a community.*

To be honest, this is my very first ASCIIDOC ... so, if you are an expert on that, you are more than welcome to help me to improve the document (see "How to contribute?")

## How to contribute?
* If you think an information is wrong, you are welcome to join the discussion
* If you find any (little) mistake etc please file an issue.
* If you would like to add, delete (outdated) or update information in the document, please use Github functions for that (fork, pull request etc).
* If you would like to translate the whole document into your language, don't hesitate to contact me (--> discussion) first. I will give you some information, what I did for the German translation etc.

### Style Consistancy
The English version is the main document. All translations SHOULD be derived from that. If you contribute, please make sure, that your work is reflected in the main version.

To have an consitant document, which can be maintained in a good way, we all should accept some points:
* Images
  * All images have an alt-text and a title attribute (except chapter images).
  * Images have an approriate copyright --> CC-BY-SA
* Chapters
  * This is a multipart ASCIIDOC. The highest level is level 0 "=".
  * The headings are from level two to four (or five?)
  * Level three has a special sign for better reading "=== • Item" and are in capital letters.
  * Every part has an image, after that there is a pagebreak "<<<" (in an own block)
  * After the pagebreak the first line repeats the part title with "[big]#Title#"
  * Every source file SHOULD end with "End of chapter" comment
* Admonitions
  * Only NOTE and IMPORTANT are used
  * If you use IMPORTANT, the text MUST be bold by "\*bold\*".
* Text
  * Every sentence in its own line.
  * Commands MUST be set monospace by "\`command\`"
  * File pathes etc SHOULD set italic by "\_path\_"
* v4 v6
  * you MUST use "IPv4" or "IPv6", not v4 or v6
  * same with DHCP: You should use DHCPv4 or DHCPv6 to clarify what you mean.
* IPv6 examples MUST use the documentation prefix 2001:db8::
* German
  * Numbering from "eins" to "zwölf" MUST be written


## What is different to the original?
There are a lot of style differences to the orignal document of ARCEP. This is based on my humble abilities in ASCIIDOC, you are welcome to help me with that.

These are some points I didn't yet find an solution for:
* Margins: Symbols in the margin. It is refelected in comments in the source code.
* Text color: Not as easy in ASCIIDOC. You can find a theme with e.g. "[.blue]", but this not in the pdf, while is in html5-export.
* Tables: Colors for the heading, whith white text-color and dark blue background-color etc
* Chapter table-of-content: There seems to be no function in ASCIIDOC for that.
* More style consistancy: I tried to hold some aspects more consistant e.g. chapter-levels, image captions etc.

## How to build a PDF?
* Install ruby
* Install asciidoctor
* Install asciidoctor-pdf ("gem install asiidoctor-pdf")
* Build HTML5 with embedded images (base64): asciidoctor --backend html5 -a data-uri main.adoc
* Bild PDF: asciidoctor-pdf -a optimize HowToDeployIPv6.adoc
  
## How to convert the original docx to ASCIIDOC?
pandoc guide-entreprises-how-to-deploy-IPv6-july-2022.docx -f docx -t asciidoc --wrap=none --markdown-headings=atx --extract-media=extracted-media -o guide_v01.adoc
