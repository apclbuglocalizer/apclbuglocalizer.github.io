---
title: User Guide
nav_order: 3
---

# User Guide
{: .no_toc }

{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Overview
The way to submit the bug report and related projects for bug localization is via a web-based submission form. The system will send you the notification email when you successfully submit the bugs and notify you via the same email after your bug localization is done. 

This web form is built based on Python Flask framework. If you are a developer and wants to deploy this tool, please refer to [Developer guide]({% link docs/configuration.md %}) on how to deploy it. 

{: .note }
Users are required to submit a `.zip` file that includes all of the source code, so the system can do the static analysis for more accurate results.

---

## Interface
![Bug Localizer Logo](/assets/images/interface.png)

---


## Instructions

1. **Prepare your files**  
   Include all source code in the projects, so the system can do the static analysis for more accurate results.  

2. **Compress into a `.zip`**  
   Place all files into a single folder and compress it into a `.zip` archive.  

3. **Name your archive**  
   Please do not include any white space in your file name.

4. **Fill out the form**  
- Please be sure the Email address is correct as the system uses the provided email for communication.
- Please provide detailed bug report. 

5. **Upload the file**  
Only `.zip` files are accepted.  

6. **Submit**  
- Click **Submit Report** and wait for the confirmation message.  
- After bug localization is done, you will receive another emial notification.
