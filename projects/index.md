---
layout: page
title: Projects - Previous Work
---

# Internship at Logitech
## February - August 2018

For my mandatory internship, I chose to work at Logitech. Originally a peripherals company, Logitech aims to get into data science and understand better eSports (since they sponsor big teams).

I worked for 6 months on a project involving Machine Learning, Data Analysis, ESports. The goal of the internship was to find the future ESport pro players. To this end, I designed a tool to automatically extract games features from game logs, ran it on a set of such logs and analyzed the result using standard ML techniques.

During this internship, I broadened my technical skills (learnt how to use Docker, GPU farms, Kubernetes, got better at C++ and Makefiles/CMake) as well as my soft skills (I attented several trainings on presentations, had to present my project several times, and got involved in meetings).

# Google Summer of Code 2017

See [the dedicated page](GSoC), I worked on the multithreading for Scala Native, and ahead of time compiler for Scala.

# Lauzhack MoodleHub

I participated to [Lauzhack 2017](http://lauzhack.com/) (Lausanne's Hackaton) with a friend. We implemented Moodlehub during the 12h of coding. You can see the code on this [Github Project](https://github.com/MoodleHub/MoodleHub). MoodleHub was concieved as a way to be able to regularly download and update data from Moodle, a web platform used by universities to let teacher upload their courses.

Using this tool enables the user to depend less on an internet connection or a regular authentication, as well as a convenient way to keep yourself updated with your courses (or download all your course contents right before exams !).

# School Work

## Semester project
### Towards easier and automatic article referencing

During my last semester of studies, I worked on my semester project with [SPRING (Security and privacy engineering) lab](https://www.epfl.ch/labs/spring/) at EPFL, supervised by [Carmela Troncoso](http://carmelatroncoso.com/) and [Wouter Lueks](https://wouterlueks.nl/).

My work consisted in finding ways to make article referecing easier and more trusted between news organizations, independent journalists and readers.

You can find my project report [here](Semester_Project/Semester_Project_Report.pdf).

## Principles of Computer Systems course
### One pagers 

As part of my curriculum, I attented the course Principles of Computer Systems at EPFL ([link to syllabus](https://dslab.epfl.ch/teaching/pocs/)). According to the course website "This course is targeted primarily at students who wish to acquire a deep understanding of computer system design or pursue research in systems". 

As this course had a prominent research component, we were asked to write "One pagers" on specific topics every other week. These One Pagers were supposed to be independant work and were aimed at answering a specific question by proposing a broad idea on how to solve the problem.

You can find two of my One Pagers here :
* [Proactive bandwidth flooding resistant internet](POCS/POCS_OP4.pdf)
* [Self-recoverable software for zero-administration](POCS/POCS_OP6.pdf).

## SHS Project (Human and Social Sciences)
### Assesment of ethical data awareness of EPFL students

As part of EPFL's curriculum, students have to follow a HSS course each Semester. During the last year of studies, we have to conduct a project according to the course we chose. I picked the course "How people learn" [(link to syllabus)](https://edu.epfl.ch/coursebook/en/how-people-learn-i-HUM-432?cb_cycle=bama_cyclemaster&cb_section=shs) as I'm interested in cognitive and social studies.

Along with my group we worked on assessing ethical data awareness of EPFL students. To do so, we designed a questionnaire and gave it to Bachelor students from different years in Computer Science or Communication Systems in order to test their hypothetical use of sensitive data depending on the type of data (e.g. DNA), the importance of the expected output of using such data (saving millions of people from different diseases).

You can find our report under the form of a Business report [here](SHS/Business_report_SHS.pdf).

## Distributed System Engineering project
### Secure and distributed rock paper and scissors using blockchains

This course was dedicated to learning usual distributed system techniques such as gossip and systems such as blockchains. The end goal of the course was to produce a group project based on the word done during the Semester.
Along with my peers Leonardo Aoun and Lucas Gauchoux, we designed a rock paper and scissors game on top of our distributed system.

The main challenge of this project was to inplement a commit system to prevent cheating as well as create incentives to play using made up money and wallets (similar to cryptocurrencies).

You can find the code for this project [on Leonardo's Github](https://github.com/aounleonardo/Rasp) and our project report [here](DSE/DSE_Project_Aoun_Gauchoux_Coudert.pdf).

## Machine Learning Project
### Implementation of a ICML conference paper's algorithms

Among a [set of scientific papers from ICML 2916](http://icml.cc/2016/?page_id=1839) I had to pick a paper that interested me, to implement its algorithm and compare it to similar ones. I chose the paper [Geometric Mean Learning](GMML.pdf) that presented a new algorithm for metric learning, using the mathematical geometric mean of geodesic curves. You can find my report and the full explanation [here](ML_project.pdf). During this project, I was able to learn more about metric learning and used python among with scikit learn and pandas to implement the algorithm, compare it to similar metric learning algorithms and compare their running time with regard to different datasets.

## Computational geometry course project
### Pattern recognition for a set of images

This project consisted in the creation of an image recognition system learning a set of 70 classes from a database of 15 pictures per class. The classifier was a KNN algorithm working on features derived from Hu moments. I done this project in cooperation with Loïs Paulin, another student. [Here](CGDI_report.pdf)'s the final report we handed in with full explanation and results.

## Distributed Systems project
### Implementation of a distributed data-manager

The goal of this project was to implement a distributed data-manager, I was to choose a topology for my distrbuted system and implement a way to ditribute data accross it with at least a bit of robustness. I implemented it in Erlang (you can find the code [on my github](https://github.com/Korf74/DS_Project). The [instructions (link)](DS_project.pdf) for the project were meant to let a lot a freedom, which I took by making use of Erlang OTP patterns. The full report for this project can be found [here](DS_report.pdf).


# Misc.
## Other Projects

* Implemented a GIMP plugin for the Canny Algorithm (ported from openCV).
* Worked on a group project in which we coded a tool to transform bitmap images into vector images.
