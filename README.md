[![Build Status](https://travis-ci.org/sci-gaia/D2.3UserForum.svg?branch=master)](https://travis-ci.org/sci-gaia/D2.3UserForum) [![Code Climate](https://codeclimate.com/github/sci-gaia/D2.3UserForum/badges/gpa.svg)](https://codeclimate.com/github/sci-gaia/D2.3UserForum) [![Issue Count](https://codeclimate.com/github/sci-gaia/D2.3UserForum/badges/issue_count.svg)](https://codeclimate.com/github/sci-gaia/D2.3UserForum)

# D2.3 User Forum

This repository contains the raw material for the [Sci-GaIA project](https://www.sci-gaia.eu) Deliverable 2.3 - Outcomes of the Web-Based User Forum. Note :

  * The main file is : **D2.3-UF.md**. This is used to build the other formats (pdf, odt - [see below](#building-the-document))
  * **Looking for PDF / DOC ?** If you want a pre-compiled document to read, in a `.pdf` or `.odt` file, see the [Github Releases](https://github.com/sci-gaia/D2.3UserForum/releases). This contains  the latest succesful build of the document.
  * **Comments** ? If you would to comment on the document, please open a topic on the forum under the [topic](http://discourse.sci-gaia.eu/t/skeleton-of-d2-3-outcomes-of-the-webbased-user-forum/2478/2)
  * **Contributions** ? If you would like to contribute to the document, please fork the repository and send your suggestions in a pull request.

#  Building the document

The document is built automatically on [Travis](https://travis-ci.org/sci-gaia/D2.3UserForum). See the [Travis file](.travis.yml) to see what is done in detail. The following steps are done :

  1. Convert images where necessary
  2. Conduct spell check
  3. Push release on successful build


## Pandoc

We use pandoc to create the document :

```
pandoc -S --filter pandoc-fignos \
--variable mainfont="Lato" \
--variable sansfont="Lato" \
--variable monofont="Roboto" \
--variable fontsize=12pt \
--variable version=1.17.2 \
--reference-odt="deliverable-template.ott" \
--number-sections \
--toc \
--from markdown+implicit_figures+table_captions+pipe_tables+footnotes+inline_notes \
D2.3-UF.md  -o D2.3-UF.odt
```

You will need the filters available in your distribution of pandoc.

#  Spell checking

We use aspell to
`cat D2.3-UF.md  | aspell --pipe --encoding utf-8|grep -v \* | uniq`

# Releases

Versions are considered internal unless they have a major version number (_e.g._ `v1.0.0`). 
