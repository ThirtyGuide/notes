# Pre-course Assignments

**R, RStudio and the tidyverse**

[← All chapters](README.md) · [Original PDF](PDF%20Slides.pdf#page=4)

## Overview

- The distinction between the R language and RStudio; installation and interface overview.
- R scripts, R Markdown, packages, libraries and reproducible workflows.
- Introductory coding tasks and data files described in the supplied materials.

## Source documents

1. [CA09 AUT26 Intro to R and RStudio.pdf](#source-1) — PDF, reader page 5
2. [WelcomeLetterCA09_AUT26.pdf](#source-2) — PDF, reader page 10
3. [CA09_AUT26_pre_programme_assignment.zip](#source-3) — ZIP, reader page 12

---

<a name="source-1"></a>

## CA09 AUT26 Intro to R and RStudio.pdf

<small>File type: PDF · Reader pages 5–9 · [View source PDF](PDF%20Slides.pdf#page=5)</small>

<small>Source Page 1 of 9</small>

### Introduction to R and RStudio

Dr. Helen Wang

R is a free, open-source programming language designed for statistical computing, data analysis, and graphical visualization. It is widely used in academia, research, and industry for tasks such as data cleaning, modeling, and visual storytelling.

RStudio, on the other hand, is an integrated development environment (IDE) that provides a user-friendly interface for working with R. RStudio allows you to write code, save it for later use, display graphics, view results of your algorithms in a single convenient display.

In short, R is the programming language itself, and RStudio is the software you use to interact with R.

This guide will walk you through how to install R and RStudio on your computer. Both are free and open source, and for most people they should be straightforward to install. Please

I.

Installing R

Go to the CRAN (Collective R Archive Network)– this is the site where R itself and most R packages live. Click on “Download R for XXX”, where XXX is either macOS or Windows:

Figure 1: R Download Homepage

[For Windows Users]

After clicking on the third link of the webpage in Figure 1, you will be taken to the download page for Windows homepage (Figure 2). Click on “install R for the first time” and you will be

<small>Source Page 2 of 9</small>

directed to the webpage as shown in Figure 3. Click on “Download R-4.6.1 for Windows” or the latest version displayed at the top of the page. Click Next through all the prompts to install like any other program. once finished, proceed to install R Studio.

Note: Note: new releases of R are made regularly, therefore please ensure that you install the latest available (stable release) version, as indicated on the CRAN homepage.

Figure 2: Download R for Windows, Webpage 1

Figure 3: Download R for Windows, Webpage 2
[For Mac Users]

First upgrade to the latest macOS version and have Xcode Command Line Tools installed on your mac. The Xcode tool is required for installing or compiling certain R packages that include C/C++ or Fortran code. To install the tool, run the following code in Terminal:

xcode

select

--

install

If you run into problems with this code, go ahead and download the Xcode App from Apple Store.

Then, click on the 2nd link on webpage of Figure 1 and you should be taken to the download page for macOS homepage, which looks like Figure 4.

Pay attention to whether you need the ARM or the x86 version. If you are on the latest Mac M1, M2 chip click on “R-4.6.1-arm64.pkg” to download the ARM version, if you have an

<small>Source Page 3 of 9</small>

older macbook that still runs on the Intel chip, click on “R-4.6.1-x86_64.pkg” to download the x86 version.

Figure 4: Download R for Mac

II.

RStudio

a. Installing RStudio

Please go to RStudio's homepage. (NOTE: You must have installed R before proceeding with the installation of RStudio). Scroll down to the bottom of the page where links for downloading RStudio for different operating systems are displayed as shown in Figure 5.

<small>Source Page 4 of 9</small>

Click Next through all the prompts to install.

Figure 5: RStudio Downloading Page

b. Layout of RStudio

Once installed, double-click on the RStudio icon to open the program. Click on “File → New File → R Script” to start a new R code file, then you will see the interface with four panes as shown in Figure 6, which is the most common layout for working with RStudio.
<small>Source Page 5 of 9</small>

Figure 6: Default RStudio Interface (Windows)

Console Pane (Bottom Left): This is where you interact directly with R. You can type and run R commands here, and the output (results, errors, etc.) will be shown immediately. For example, try typing “5 + 3”.

Script Pane (Top Left): This is where you write and edit scripts, i.e., files containing code.

You can run code line-by-line or in chunks into the Console. Note: there are two types of files that we will be working with:

- R Script (.R file) is to be used when you are writing code for yourself. It consists of code

and simple textual comments. It is more of a "developer" style of coding.

- R Markdown (.Rmd file) is typically used when you plan to share your work with me, a

colleague at work or in a presentation. It contains all the code, the results of running chunks of code, output images etc. When the file is completed, you can knit it to a pdf or an html format which you can share e.g. upload to Canvas.

Workspace Pane (Top Right):

- The Environment tab shows all active variables, data frames, and functions currently in

memory.

- The History tab lists all previously run commands, which you can reuse.

<small>Source Page 6 of 9</small>

Display Pane (Bottom Right):

graphics generated during session using Rcharts, htmlwidgets). Cannot be used for viewing online information.

- The Files tab allows you to browse and manage files in your working directory.

- The Plots tab allows you to view charts and graphs generated by your code.

- In the Packages tab you can see installed packages and load/unload them.

- In Help tab you can access documentation for R functions and packages.

- The Viewer tab renders local web content in the form of static HTML pages (e.g. web

III.

Packages

R packages are collections of functions, data, and documentation that extend the capabilities of base R. They allow you to perform specialized tasks without writing code from scratch.
The tidyverse is a collection of R packages designed for data analytics. These packages share a common philosophy, consistent grammar, and are built to work together. The tidyverse helps you with tasks like data cleaning, transformation, visualization, and modeling. For example, ggplot2 is a package in the tidyverse which we will rely on for data visualization in this course.

Please complete the courses “Introduction to the Tidyverse” and “Introduction to Data Visualisation with ggplot2” on Datacamp.

a. Installing tidyverse

You need to install all the packages you need before you can use them. As an example, I will show you the steps of installing tidyverse.

To install tidyverse, go to the Display Pane and click on the Packages tab. Click on the “Install” button, and you will be directed to the window as displayed in Figure 8. Enter “tidyverse” (or any other package names later when you need them) in the “Packages” field, make sure to check the “Install dependencies” box, and click on “Install”.

<small>Source Page 7 of 9</small>

Figure 7: The Packages Tab of Display Pane

Figure 8: Installing tidyverse

b. Loding tidyverse

Once a package is installed on your machine it is saved in a directory called library. In order to use a package within RStudio it first needs to be loaded from the library using a command. Enter the following code in your Script Pane and run it by clicking on the green arrow-like “run” button on the top right side of the pane:

```r
library("tidyverse")
```

<small>Source Page 8 of 9</small>

You will see outputs in the Console Pane telling you what packages have been loaded, as shown in Figure 9.

Figure 9: Loding tidyverse

IV. Posit AI Assistant

From the 2026 version, RStudio has enabled an AI coding assistant function. It works more like an AI agent inside RStudio: it can see your R session, variables, console output, plots, and code, so you can ask it to write/debug R code, explain errors, explore a dataset, create visualisations, or help build models.
To enable the AI assistant, click on the Posit Assistant button at the top right of the screen (Figure 9), then click on “Install Posit Assistant” (Figure 10). Click on “Sign in to try Posit AI for free” (Figure 11) and follow the instructions.

You will get a 30-day free trial of Posit AI with a limited number of tokens. You can later switch to the $20 per month Pro subscription to get more tokens.

Figure 9: Posit Assistant Button

<small>Source Page 9 of 9</small>

Figure 10: Install Posit Assistant

Figure 11: Posit Sign In


[↑ Back to the source list](#source-documents)

---

<a name="source-2"></a>

## WelcomeLetterCA09_AUT26.pdf

<small>File type: PDF · Reader pages 10–11 · [View source PDF](PDF%20Slides.pdf#page=10)</small>

<small>Source Page 1 of 3</small>

### (Not Graded)

Dear --------,

Welcome to the Data Analytics for Finance pre-programme course! This letter contains information on installing R and RStudio, getting access to Datacamp, as well as instructions for your pre-programme assignment.

- Installation of R and RStudio

We will be using R programming language for this course, so the first thing you have to do is install R (the programming language itself) and RStudio (front end using which you will write your code) on your computer. You can find step-by-step instructions in the supplementary pdf document which I have written for you called "Introduction to R and RStudio" (Section I and II).

Once you install R and RStudio, you should install the Tidyverse Package, as detailed in Section III of my introductory pdf.

- Datacamp Courses

We will be using Datacamp and you should register to ‘CA09 2026’ course using the following link (please copy and paste the entire link in your browser):

https://www.datacamp.com/groups/shared_links/24b8868c3119de3b26c5d77636 f0f3f39359a7b063a119eb7e48457ed9e04c73

Once you join the link, your assignments should be visible in the "Assignments" tab. If not, you can also search for them manually by assignment name (e.g. Introduction to R). In case of any other issues, please contact me via email (state that you are from CA09 course) to

As part of the pre-programme, you are asked to complete the following Datacamp courses:

- Introduction to R - Introduction to the Tidyverse - Introduction to Data Visualisation with gg‐

plot2

<small>Source Page 2 of 3</small>

Taking notes based on what you cover is not required, but please do so if you feel you will benefit.

Please note retention of the material will not be perfect the first time through. The only way to really retain the material is via lots of practice/doing.
Each should take you about 2-4 hours to complete. You can start any Datacamp course, log out part way through, and come back and finish it later from the same point.

DataCamp is meant to be low stakes-practice, so the only thing that matters is your learning. You should take as many hints/solutions during your Datacamp practice as much as you need.

- Pre-programme assignment

You are requested to submit an individual assignment which you should attempt after completing the Datacamp courses.

- Download the zipped file CA09_AUT26_pre_programme_assignment.zip.

- When you unzip and save it locally, you should be able to see that it contains one

RMD file called your-name_pre_programme_assignment.Rmd and a folder, Data, that contains data relevant to this assignment.

- Open your RStudio. Ensure you have tidyverse package installed on your computer. If

you try to load a package, for example:

```r
library(tidyverse) and R gives an error stating that the package is missing, use the
“Packages” panel in RStudio to install it.
```

- Rename the R Markdown file named your-

name_pre_programme_assignment.Rmd to your first name and last name Firstname_Lastname.Rmd and open it in RStudio.

- Complete the tasks given in the R Markdown, Rmd file. Write your own short bio‐

graphy using markdown, fill out code in the empty chunks provided, (you can definitely copy, paste, and adapt from online resources such as https://moderndive.com and DataCamp!), and answer all questions. There are many placeholders (marked with question marks, ???) throughout the document where you should type answers. Please delete the questions and rewrite the text to be more narrative. So instead of keeping the instructions and hints, remove them, and write things like “My analysis shows…”

When you’re all done, click on the “Knit” button at the top of the editing window and create a pdf document or HTML file of your assignment and upload it to Canvas, together with your Rmd file.

Hint: If you install the tinytex package, you should be able to knit your work to a PDF file.

<small>Source Page 3 of 3</small>

Human-AI collaboration is becoming the new coding modality. Feel free to use AI assistance while coding, such as Posit Assistant (see installation instructions in Intro to R and Rstudio document) and ChatGPT ( provides ------- subscription).

If you have any questions, please email me (Dr. Helen Wang) at I hope you enjoy your first coding tasks in R!


[↑ Back to the source list](#source-documents)

---

<a name="source-3"></a>

## CA09_AUT26_pre_programme_assignment.zip

<small>File type: ZIP · Reader pages 12–12 · [View source PDF](PDF%20Slides.pdf#page=12)</small>

> This is an extracted preview or inventory, not the complete underlying file.

<details>
<summary>Open extracted source preview</summary>

> Archive contents: 4 entries. This is an inventory, not the full contents of the nested archive.

CA09_AUT26_pre_programme_assignment/

CA09_AUT26_pre_programme_assignment/Data/

CA09_AUT26_pre_programme_assignment/Data/DGS10.csv

CA09_AUT26_pre_programme_assignment/your-name_pre_programme_assignment.Rmd

- 

- 

- 

- 

</details>


[↑ Back to the source list](#source-documents)

---

