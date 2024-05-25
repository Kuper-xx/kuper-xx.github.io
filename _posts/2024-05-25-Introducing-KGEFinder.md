---
title: Introducing KGEFinder
published: true
---

[Link to index page](/).

<h1 align="center">
    <img src="https://raw.githubusercontent.com/Kuper-xx/KGEFinder/main/static/example.png" alt="kgefinder" width="600px">
</h1>

## [](#header-1)Introduction

In the realm of Open Source Intelligence (OSINT), finding email addresses can be a crucial step for investigations, outreach, or data analysis. To streamline this process, I've developed [KGEFinder](https://github.com/Kuper-xx/KGEFinder), a powerful and efficient tool designed to locate email addresses with ease by simply giving a Github username. Today, I'm excited to introduce you to KGEFinder, explain it, and guide you through its usage.

## [](#header-2)Why KGEFinder?

KGEFinder stands out due to its:

* Efficiency: Quickly sifts through data to find relevant email addresses.
* User-Friendly: Simple command-line interface for ease of use.
* Open Source: Freely available on GitHub for customization and improvement.


## [](#header-3)Getting Started

* Installation:
First, clone the repository from GitHub:
```bash
git clone https://github.com/Kuper-xx/KGEFinder.git
```
Navigate to the directory and install the necessary dependencies:
```bash
cd KGEFinder
pip install -r requirements.txt
```

## Tutorial: Finding Emails with KGEFinder
You just have to execute the python file:
```bash
python KGEFinder.py
```
And then the console will ask you to enter a Github username, you enter the mail and press 'Enter' and wait, the program will do all the work for you.

Finally you will see a message like this with the username personal email:
```bash
===========================================
[*] Email Found: example@example.com
===========================================
```
Or the program give you an error.

## Errors:
The program can say to you:
### [!] The username does not exist.

* This means that the username has a typo or the username you provided does not exist on Github.

### [!] Email not found.

* This means the Github username you enter does not have repositories or, the commits are verified.

### [!] Error. 666

* This error means that there are not any commit in the repository.

### [!] Error. 777

* This error means there is a problem extracting the email from the patch file of the Github commit.

## Contributing and Feedback
KGEFinder is an open-source project, and I welcome contributions and feedback. If you encounter any issues or have suggestions for improvement, please create an issue on the [GitHub repository](https://github.com/Kuper-xx/KGEFinder/issues) or submit a pull request.


_Happy Email Finding! :)_ 