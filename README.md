![Version](https://img.shields.io/static/v1?label=manuscriptInTypst&message=0.2&color=brightcolor)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

# First submission manuscript template in typst

## Purpose

Prepare PDF for initial submission of a manuscript.

## Features

- line numbering
- single- and double-spacing
- short author list and running title in header
- 1/N page numbering
- biblatex
- example
  + figure
  + table
  + equation 

## Sample of first page

<img width="1582" alt="Screenshot 2024-10-11 at 10 06 08 PM" src="https://github.com/user-attachments/assets/c37c819f-6199-4092-bfaf-4d6a115b1f76">


## Contents
- typst source file template
- biblatex file
- sample PDF


## Requirements

- typst version 0.12.0 (pre-release from GitHub site, required for line numbers) 

## Bash or zsh function to project initiation (optional)

Paste into whereever you store your bash functions (.e.g., .bashrc or .bashFunctions sourced from .bashrc).
Customized the filepaths to meet your needs.

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
cp  ~/6112MooersLabGitHubLabRepos/manuscriptInTypst/first-submission-manuscript.typ manu$1.typ
cp  ~/6112MooersLabGitHubLabRepos/manuscriptInTypst/first-submission.bib manu$1.bib
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
cp  ~/6112MooersLabGitHubLabRepos/manuscriptInTypst/first-submission-manuscript.typ manu$1.typ
cp  ~/6112MooersLabGitHubLabRepos/manuscriptInTypst/first-submission.bib manu$1.bib
say 'The manuscript template has been copied.'
}
```




## Update history

|Version       |Changes                                                                                               |Date                 |
|:-------------|:-----------------------------------------------------------------------------------------------------|:--------------------|
| Version 0.1  | Initiate project. Added badges, funding, and update table.                                           | 2024 October 11     |
| Version 0.2  | Added bash function to ease initiating new manuscript in typst.                                           | 2024 October 13     |

## Sources of funding

- NIH: R01 CA242845
- NIH: R01 AI088011
- NIH: P30 CA225520 (PI: R. Mannel)
- NIH: P20 GM103640 and P30 GM145423 (PI: A. West)
