---
id: "GtkTut"
title: The Perl6 GTK+ Tutorial
author: Marcel Timmerman
date: Version 0.0.1, March 25, 2019
keywords: perl6,gtk,gtk3,gtk+,gdk,glib,glade
#output: pdf_document
output:
  pdf_document:
    #path: Tutorial.epub
    #path: Tutorial.pdf
    papersize: A4
    toc: true
    toc-depth: 6
    #cover-image: images/widgets-1.png
    pandoc_args: [
      '-f markdown+fenced_code_attributes+tex_math_single_backslash',
      #'--css=Style/Tutorial.css',
      '--pdf-engine=pdflatex',
      '--strip-comments',
      '-o Tutorial.pdf'
    ]
fontsize: 12pt

export_on_save:
  pandoc: true

toc:
  depth_from: 1
  depth_to: 6
  ordered: true

ebook:
  title: The Perl6 GTK+ Tutorial
  authors: Marcel Timmerman
  tags: perl6,gtk,gtk3,gtk+
  epub:
    no-default-epub-cover: false
    pretty-print: true
---
<!--
pandoc -o Tutorial.pdf\
  -f markdown+fenced_code_attributes+tex_math_single_backslash\
  --pdf-engine=pdflatex --strip-comments\
  Tutorial.md Parts/simple-example.md Parts/installation.md\
  Parts/basics.md

pandoc -o Tutorial.pdf\
  Tutorial.md Parts/simple-example.md Parts/installation.md\
  Parts/basics.md
-->

# Preface {ignore=true}
This tutorial is about using the Graphical User Interface library **GTK+** while writing code in the programming language **Perl6** instead of **C** in which the library is written. There are a few packages written to help you with that. This tutorial will first explain the modules in the package `GTK::V3` and then the modules from `GTK::Glade`. The first is about building your GUI on your own and the latter is about making use of the generated *XML* file from the GTK+ GUI designer program *Glade*. At the end of the tutorial some of the design ideas of GTK::V3 are explained followed by a reference of the modules.

<!--
[toc]
# Table of Contents
1. Installation

1. Getting Started
   1. Simple example 1
   1. Simple example 2

1. Conventions in GTK::V3
   1. Naming of methods
   2. Types used in GTK+

1. Basics
   1. Main Loop
   3. GtkMain
   2. GObject

1. Containers
   1. GtkBin
   1. GtkGrid
   1. GtkListBox

1. Design
   1. Class Tree
   1. Fallback
   1.

1. GTK::Glade
   classes
   class engines
   testing
   inspector

1. Reference
   1. GTK::V3
   1. GTK::Glade
-->

<!-- @import "Parts/simple-example.md" -->

<!-- @import "Parts/installation.md" -->

<!-- @import "Parts/basics.md" -->
