# Designing the Data Science Classroom

### rstudio::conf 2022

by Mine Çetinkaya-Rundel + Maria Tackett

------------------------------------------------------------------------

:spiral_calendar: July 25 and 26, 2022  
:alarm_clock: 09:00 - 17:00  
:hotel: [ADD ROOM]  
:writing_hand: [rstd.io/conf](http://rstd.io/conf)

------------------------------------------------------------------------

<<<<<<< HEAD
## Overview

Success in data science and statistics is dependent on the development of both analytical and computational skills, and the demand for educators who are proficient at teaching both these skills is growing. The goal of this workshop is to equip educators with concrete information on content, workflows, and infrastructure for painlessly introducing modern computation with R and RStudio within a data science curriculum.

In addition to gaining technical knowledge, participants will engage in discussion around the decisions that go into developing a data science curriculum and choosing workflows and infrastructure that best support the curriculum and allow for scalability. Workshop attendees will work through several exercises from existing courses and get first-hand experience with doing and teaching data science with the tidyverse and tidymodels packages. Attendees will also get experience using relevant tool-chains and techniques, including running a course on RStudio Cloud, literate programming with Quarto, and workflows for collaboration, version control, and automated feedback with Git/GitHub. We will also discuss best practices for configuring and deploying classroom infrastructures to support these tools.

This workshop is aimed primarily at participants teaching data science in an academic setting in semester-long courses, however much of the information and tooling we introduce is applicable for shorter teaching experiences like workshops and bootcamps as well. Basic knowledge of R is assumed and familiarity with the tidyverse and Git is preferred.

## Learning objectives

Curriculum, workflow, and infrastructure design for teaching data science with R and RStudio.

## Is this course for me?

If your answer to any of the following questions is “yes”, then this is the right workshop for you.

-   Do you want to learn / discuss curriculum, pedagogy, and computing infrastructure design for teaching data science with R and RStudio?

-   Are you interested in setting up your class in RStudio Cloud?

-   Do you want to integrate version control with git into your teaching and learn about tools and best practices for running your course on GitHub?

## Prework

NOTE: ADD LINK TO VIDEO ON LET THEM EAT CAKE FIRST

In this workshop you will wear two hats: the educator and the learner. At times I will be demoing workflows for instructors (whom I assume are familiar with R, RStudio, and the tidyverse and have taught with or are interested in teaching with RStudio Cloud, Git, and GitHub) and at other times you will be working through the student view (on RStudio Cloud, assuming you're not using your local setup).

For the former, you'll need to come prepared. For the latter, you can assume you're a student in an intro data science course and this is the first day of class (i.e. there's no expectation of prep).

So, let's focus on the former -- the instructor view. The list of items you should complete prior to the workshop can be found below. If you need help with any of the steps, please ask on the [RStudio Community thread about this workshop](https://community.rstudio.com/t/designing-the-data-science-classroom-workshop-rstudio-conf-2020).

**Note:** These steps will direct you to relevant chapters from "Happy Git with R" by Jenny Bryan et. al. It's such a great and comprehensive resource that I have not felt the need to replicate the information elsewhere.

-   [Register a free GitHub account](https://happygitwithr.com/github-acct.html#github-acct)
-   [Install or update R and RStudio](https://happygitwithr.com/install-r-rstudio.html#install-r-rstudio)
-   [Install Git](https://happygitwithr.com/install-git.html#install-git)
-   [Introduce yourself to Git](https://happygitwithr.com/hello-git.html#hello-git)
-   [Prove local Git can talk to GitHub](https://happygitwithr.com/push-pull-github.html#push-pull-github)
-   [Cache your username and password or set up SSH keys](https://happygitwithr.com/credential-caching.html#credential-caching)
-   [Create and save a GitHub Personal Access Token (PAT)](https://happygitwithr.com/credential-caching.html#credential-caching)
-   [Prove RStudio can find local Git and, therefore, can talk to GitHub](https://happygitwithr.com/rstudio-git-github.html#rstudio-git-github)

Finally, specific to this workshop:

-   Install and load the following packages:
    -   From CRAN:

<!-- -->

    install.packages("devtools")
    install.packages("DiagrammeR")
    install.packages("DT")
    install.packages("flesdashboard")
    install.packages("gapminder")
    install.packages("learnr")
    install.packages("lubridate")
    install.packages("infer")
    install.packages("magick")
    install.packages("nycflights13")
    install.packages("rvest")
    install.packages("shiny")
    install.packages("sortable")
    install.packages("tidyverse")
    install.packages("unvotes")

-   From GitHub:

<!-- -->

    devtools::install_github("gadenbuie/countdown")
    devtools::install_github("OpenIntroStat/openintro-r-package")
    devtools::install_github("rundel/ghclass")
    devtools::install_github("rstudio/parsons")

## RStudio Cloud

The RStudio Cloud workspace is at [INSERT LINK].

## Schedule

### Day 1

| Time          | Activity                                                 |
|:--------------|:---------------------------------------------------------|
| 09:00 - 10:30 | Welcome + Curriculum design + Meet the toolkit [Mine]    |
| 10:30 - 11:00 | *Coffee break*                                           |
| 11:00 - 12:30 | Teaching data science with the tidyverse [Mine]          |
| 12:30 - 13:30 | *Lunch break*                                            |
| 13:30 - 15:00 | Teaching modern modeling with tidymodels [Maria]         |
| 15:00 - 15:30 | *Coffee break*                                           |
| 15:30 - 17:00 | Interactivity and immediate feedback with learnr [Maria] |

### Day 2

| Time          | Activity                                                   |
|:--------------|:-----------------------------------------------------------|
| 09:00 - 10:30 | Computing infrastructure with RStudio Cloud [Mine]         |
| 10:30 - 11:00 | *Coffee break*                                             |
| 11:00 - 12:30 | Reproducible workflows: Quarto, Git, GitHub [Mine + Maria] |
| 12:30 - 13:30 | *Lunch break*                                              |
| 13:30 - 15:00 | Making a data package [Mine]                               |
| 15:00 - 15:30 | *Coffee break*                                             |
| 15:30 - 17:00 | Organizing teaching materials + Wrap-up / Q&A [Maria]      |

## Instructors

Mine Çetinkaya-Rundel is Professor of the Practice at Duke University and Developer Educator at RStudio. Mine’s work focuses on innovation in statistics and data science pedagogy, with an emphasis on computing, reproducible research, student-centered learning, and open-source education as well as pedagogical approaches for enhancing retention of women and under-represented minorities in STEM. Mine works on integrating computation into the undergraduate statistics curriculum, using reproducible research methodologies and analysis of real and complex datasets. Mine works on the OpenIntro project, whose mission is to make educational products that are free, transparent, and lower barriers to education. As part of this project she co-authored four open-source introductory statistics textbooks. She is also the creator and maintainer of datasciencebox.org and she teaches the popular Statistics with R MOOC on Coursera. Mine is a Fellow of the ASA and Elected Member of the ISI as well as the winner of the 2021 Robert V. Hogg Award for For Excellence in Teaching Introductory Statistics.

Maria Tackett is an Assistant Professor of the Practice in the Department of Statistical Science at Duke University. Prior to joining the faculty at Duke, Maria earned a Ph.D. in Statistics from the University of Virginia and worked as a statistician at Capital One. Her current work focuses on understanding how active learning strategies can be used to promote engagement and student motivation in undergraduate statistics courses. She also studies how classroom practices in introductory math and statistics courses impact students’ sense of community, self-efficacy, and learning outcomes. Maria is an RStudio certified trainer and is actively involved in the R and statistics education communities.
=======
This repository contains materials for the "Designing the Data Science Classroom" workshop at rstudio::conf(2022). See [https://rstd.io/teach-ds-conf22](rstd.io/teach-ds-conf22) for rendered workshop materials.
>>>>>>> b6261aa7b4335e246e7d1bbfc0e960e179528041

------------------------------------------------------------------------

![](https://i.creativecommons.org/l/by/4.0/88x31.png) This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).
