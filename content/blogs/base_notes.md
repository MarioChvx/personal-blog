---
author: "Mario Chavez"
title: "Best way to take notes"
description: "A guide to take notes using R Markdown (Markdown/Latex) and Pandoc"
date: 2023-02-15
image: /images/blogs/base_notes/cover_base_notes.jpg
draft: false
tags:
    - latex
    - markdown
    - rmarkdown
    - pandoc
toc: true
mathjax: false
---

For math subjects I have the problem that my hand writing is slow and not very readable so I tyred a few methods to rewrite my notes or take notes in class, I found that writing notes with Word or Google Docs was extremely slow. The solution I found was **rmarkdown**, a format that combines Markdown for plain text formatting and latex syntax for math writing.

## How to use it?

The easiest way to use it is creating a Markdown file as usual but opening it with Visual Studio Code you just need to open the preview window by clicking on the icon or pressing `Ctrl + K V` or `Shift + Ctrl + V`.

![Visual Studio Code rmarkdown preview](/images/blogs/base_notes/vscode_preview.png)

## What if you want to share it?

If you have the need to send it to some one who does not have a lot of tech knowledge, you can use Pandoc ([universal document converter](https://pandoc.org/MANUAL.html)) to convert it to PDF, HTML and ton of different formats.

To install Pandoc for Windows go to the official page and download the installer, for Linux run the next command:

```bash
# Run this for Ubuntu/Debian:
sudo apt install pandoc

# And this for Arch:
sudo pacman -S pandoc
```

### Convert to PDF using Pandoc

To convert to PDF a rmarkdown file, Pandoc first convert your file to a Latex file
and then it convert it to PDF. So Pandoc will need that you have installed some version of TEX for your OS.

For Windows search for  *"miktex"* and download the executable installer.

For Linux run the following command:

```bash
# Run this for Ubuntu/Debian:
sudo apt install texlive-full 

# And this for Arch:
sudo pacman -S texlive-full
```

**NOTE**: you can use just `texlive` package and install the other ones you need to save space.

Then to convert the files just run this command:

```bash
pandoc -V geometry:margin=.5in /path/to/the_file.md -o /path/to/the_output_file.pdf
```

This will set a margin of 0.5 inches to the PDF file.

The command is kinda long so I define a function `mdtopdf()` in `.bashrc` to run it easier.

```bash
function mdtopdf() {
    echo $1;
    pandoc -V geometry:margin=.5in $1.md -o $1.pdf
}
```

To run int just type `mdtopdf file_name`

Take in count that rmarkdown is a lot more customizable than Markdow, you can read this useful [documantation](https://bookdown.org/yihui/rmarkdown-cookbook/) to get a better documents.
