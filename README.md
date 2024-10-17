![Version](https://img.shields.io/static/v1?label=manuscriptInTypst&message=0.5&color=brightcolor)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

# First submission manuscript template in typst

## Purpose

Prepare PDF for initial submission of a manuscript by using typst, a typesetting system written in Rust. Typst compiles small documents faster than LaTeX. This project is developed enough to support preparing manuscripts of journal articles for first submission. Its support for edge cases is underdeveloped.

## Features
- Barebones (i.e., no template file) for simplicity
- Two variants: classic and arvix-like.
- Line numbering
- Short author list and running title in header. This supports editing printed copies of multiple manuscripts while travelling.
- 1/N page numbering
- Biblatex (sorry, not support for BibTeX).
- example
  + figure
  + table
  + equation 

## Sample title page of classic variant

![ClassicTitle](https://github.com/user-attachments/assets/5f5e2da9-a764-4a19-8c9f-0dea23cc9298)

The footnote with the corresponding author's contact information is not shown.


## Sample Introduction page of classic variant

The abstract is on the second page.
The Introduction starts on the third page.
Note the short author list, running title, and today's date in the header.
Note the format of the page numbers in the lower right.

![ClassicIntroduction](https://github.com/user-attachments/assets/1f7bd37f-e2a4-4407-ac05-beaa75386b9e)




## Sample of first page of arvix-like variant


<img width="1582" alt="Screenshot 2024-10-11 at 10 06 08 PM" src="https://github.com/user-attachments/assets/c37c819f-6199-4092-bfaf-4d6a115b1f76">


## Contents
- typst source file template
- biblatex file
- sample PDF


## Requirements

- typst version 0.12.0 (pre-release from GitHub site, required for line numbers) 

If you use tiny mist, you will need the corresponding prerelease version.

## Easy-peasy use

Run in typst.app on-line or run via tinymist (e.g., `tinymist preview classic.typ`) while classic.typ is open in any text editor.
The rendered version will appear in your default browser.
It updates with each save operation in the text editor.

Compile to PDF by entering in terminal `typst compile <filename>.typ`.

## Bash or zsh function to project initiation (optional)

Paste into where ever you store your bash functions (.e.g., .bashrc or .bashFunctions sourced from .bashrc).
Customize the file paths to meet your needs.
Default to opening the classic variant. 
This is what most biology journals expect.
In computer science, use the arvix-like variant.

```bash
function typman {
echo "Copy template manuscript in typst with project number in title."
if [ $# -lt 1 ]; then
  echo 1>&2 "$0: not enough arguments"
  echo "Usage1: typman projectID"
  return 2
elif [ $# -gt 1 ]; then
  echo 1>&2 "$0: too many arguments"
  echo "Usage1: typman projectID"
  return 2
fi
projectID="$1"
echo "Write manuscript to manu$1.typ file."
cp  ~/6112MooersLabGitHubLabRepos/manuscriptInTypst/classic-first-submission-manuscript.typ manu$1.typ
cp  ~/6112MooersLabGitHubLabRepos/manuscriptInTypst/first-submission.bib .
cp  ~/6112MooersLabGitHubLabRepos/manuscriptInTypst/words10.png .
}

function mantyp {
echo "Copy template writing manuscript in typst with project number in title."
if [ $# -lt 1 ]; then
  echo 1>&2 "$0: not enough arguments"
  echo "Usage1: mantyp projectID"
  return 2
elif [ $# -gt 1 ]; then
  echo 1>&2 "$0: too many arguments"
  echo "Usage1: mantyp projectID"
  return 2
fi
projectID="$1"
echo "Write manuscript to manu$1.typ file."
cp  ~/6112MooersLabGitHubLabRepos/manuscriptInTypst/classic-first-submission-manuscript.typ manu$1.typ
cp  ~/6112MooersLabGitHubLabRepos/manuscriptInTypst/first-submission.bib .
cp  ~/6112MooersLabGitHubLabRepos/manuscriptInTypst/words10.png .
say 'The manuscript template has been copied.'
}
```

## Use in Emacs

Install the `typst-ts-mode` package beforehand.


## Update history

|Version       |Changes                                                                                                                  |Date                         |
|:-------------|:------------------------------------------------------------------------------------------------------------|:--------------------------|
| Version 0.1  | Initiate project. Added badges, funding, and update table.                                  | 2024 October 11     |
| Version 0.2  | Added bash function to ease initiating new manuscript in typst.                          | 2024 October 13     |
| Version 0.3  | Added classic version.  Added date to running title. Centered title on title page  | 2024 October 17     |

## Sources of funding

- NIH: R01 CA242845
- NIH: R01 AI088011
- NIH: P30 CA225520 (PI: R. Mannel)
- NIH: P20 GM103640 and P30 GM145423 (PI: A. West)
