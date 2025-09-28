Contributing Guidelines – BIOL 522: Bioinformatics for NGS Data Analysis

Welcome to the BIOL 522 course repository. This repo is both a teaching tool and a workspace for your assignments and projects.

To keep everything organized, please follow these contribution rules when working in this repository.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

🔀 Workflow Overview

1\. Fork the repository to your own GitHub account.

2\. Clone your fork to your local machine.

3\. git clone https://github.com/feseha-btc/BIOL522-NGS.git

4\. cd BIOL522-NGS

5\. Create a branch for your work. Branches should follow the format:

6\. firstname-\*\*-assignmentX #(where \*\* are your first and middle initials)

Example: alex-smith-assignment1

7\. Do your work in your branch. Place files in the appropriate folders (assignments/, projects/, scripts/).

8\. Commit changes with clear messages:

9\. git add .

10\. git commit -m "Added Assignment 1: FASTQ parsing script"

11\. Push your branch to your fork:

12\. git push origin firstname-\*\*-assignmentX        # \*\* as above

13\. Submit a Pull Request (PR) from your branch (on your fork) to the main course repository.

o Title your PR: Assignment X – Firstname Lastname

o Add a short description of what your submission includes.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

📂 Repository Organization

• assignments/ → Place weekly assignment submissions here.

• projects/ → Place all final project files (scripts, data notes, README).

• scripts/ → Reusable scripts for course demos or shared utilities.

• tutorials/ → Course-provided exercises only (do not modify).

⚠️ Important: Do not modify files outside your assignment or project folder unless instructed.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

✍️ Code \& Documentation Standards

• File names: Use lowercase letters, numbers, and underscores (snake\_case).

• Scripts: Include a header with your name, date, and description. Example:

• #!/bin/bash

• # Author: Alex Smith

• # Date: 2025-10-01

• # Description: Script for trimming FASTQ files using Cutadapt

• Python scripts: Use .py extension and follow PEP 8 style as much as possible.

• Documentation: Each assignment/project folder must include a README.md explaining:

o Purpose of the task

o Commands/scripts used

o Output description

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

✅ Submissions

• Assignments: Submitted via Pull Request by the deadline listed in the syllabus.

• Final Project:

o Proposal (Week 6)

o Progress checkpoint (Week 11)

o Final project (Week 14): must include scripts, analysis notes, and a project README.md.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

📌 Tips for Success

• Pull the latest changes from the main repo frequently to stay up to date:

• git remote add upstream https://github.com/<org-or-instructor>/BIOL522-NGS.git

• git pull upstream main

• Commit often, with small logical changes.

• Use .gitignore for large or temporary files (datasets will not be stored directly in this repo).

• Ask questions early if you are unsure about Git or GitHub workflow.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

👩🏽‍🏫 Instructor \& TAs

• Pull Requests will be reviewed by the instructor or TAs.

• Feedback will be provided directly on GitHub.

• Merged PR = assignment accepted.



