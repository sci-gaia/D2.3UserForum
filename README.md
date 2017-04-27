[![Build Status](https://travis-ci.org/sci-gaia/D2.3UserForum.svg?branch=master)](https://travis-ci.org/sci-gaia/D2.3UserForum)

# D2.3UserForum

Deliverable 2.3 - Outcomes of the Web-Based User Forum

The main file is : **D2.3-UF.md**. This is used to build the other formats (pdf, odt - [see below](#building-the-document))


#  Spell checking

`cat D2.3-UF.md  | aspell --pipe --encoding utf-8|grep -v \* | uniq`

#  Building the document

Use pandoc to create the document.

`pandoc -N --variable mainfont="Lato" --variable sansfont="Lato" --variable monofont="Roboto" --variable fontsize=12pt --variable version=1.17.2 D2.3-UF.md  --toc -o D2.3-UF.odt`

# Releases
