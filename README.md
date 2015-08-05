# Cherries
Honestly, I purely despise git since it has yet to prove itself more than a PITA

This repo is a way for me to keep my own various changed files either unique or modified from those in pcbsd docs repo.

# Test/view the pcbsd_style theme

Copy the directory _themes_ and all of its contents into the src-qt/docs directory.
Copy or modify the conf.py to match the one here (locate it in src-qt/docs)

Rebuild both/either html and/or singlehtml:
  sphinx-build -b html . _build

I use a local script such as below:

\#!/bin/sh
rm -rfI /wassup/built-docs/"$1"/"$2"/*
sphinx-build -b "$1" . /wassup/built-docs/"$1"/"$2"

The first value would be html or singlehtml (or any other format sphinx-build would know) and the second value is a way for me to keep pcbsd_style seperate from other theme builds (including as built from original).
