# White paper- Back-End Architecture

## Title: Comparative Analysis of: Virtual Machines, Dockers and Services
*  **Name:** Joseph Tolley
*  **Course/Semester/Section**: CSE 397 Professional Carer Projects: Spring 2026
*  **Instructor**: Brother Clements
*  **Date**: 06/05/2026

## Summary: 
* These are all versions of hosting the structure and operation of back-end systems. 
## Introduction: 
*  The purpose of this paper is to compare and contrast between different systems. This is essential because each offers its own strengths and weaknesses. It will be essential to our deployment which system we want to use.
*  Virtual machines are fully capable platforms with their own operating system. Docker is a way to package and create images of the backend, along with dependencies and share the same OS as the host. Systems refers to
*  sites such as render or aiven to host your back-end and database online. 
## Overview: 
**  If you have ever run Ubuntu on your windows, you have run a virtual machine. Docker provides a more lightweight approach that is easier to distribute, while VM's might be used more commonly amongst all users, Docker is
 one that is more exclusively for developers. Services provided are generally the most compassionate on the user, handling the structure and intricate details and providing a service that someone with or without
 development experience can utilize. These are sometimes free to use, but generally are not and are provided by a company to optimize your own business. 
## Strength and Weakness: 
*  VM's are the most isolated security wise, they also offer the most control to the user and can even run multiple operating systems. They are resource heavy and more difficult to scale up, I see it as better in a development
 stage, but weak as far as portability and deployment.
*  Docker is more abstract in use, but much better for deployment, scaling up, and smooth operation. They require little resources from the user and don't need much to start and run. The nice thing about Docker is that it
 can ship out everything that is needed to run the project without all the extra structure that a VM requires. It also provides a standard approach to dependencies such that if it runs on your computer, it will run
 on someone else's.
*  Services are veru useful for your average person with limited knowledge of development. Not to say that they are not useful for the experienced user, they are and can speed up production seamlessly.  They are
 like tools one can use to build, you can use a lawnmower without needing to know all the intricities of how it works. They do the heavy
 lifting for you by hosting your program and a lot of the system administration is handled by them. They are modular in nature so that one service can handle the database, another the server, etc.
# Useage and Application 
* All can be used for development and distribution of a project. A VM is stronger with security and working on older systems, but it is heavy with overhead and resource usage. Docker is a good mix of portability
 and consistency. Web services have the most support generally, but they can be an unnecessary cost or more than you might actually need. They do have the added benefit of being
 someone else's product and has an interest in keeping it working optimally. 
* I would use a VM if I needed more control, security, and if working on outdated products. I would use docker to have a more collaborative project. It can be deployed to different areas and still perform the same for each
   developer. Web services along with docker are relatively easy to scale up. I also would use web services when wanting to host something online without needing to provide the hardware to make it run. A VM is probably most
   suitable for smaller project whereas the other two are better for building something lightweight and ditributable.

# Comparison: 
* Rather than use a VM you could always use dedicated hardware whose purpose is the project. They would not be very adaptable though and if you needed to run a different operating system you might have to re-establish everything.
* Docker has competition from other services such as Github, Kubernates, Nomad, or Podman. Personal preference is often the most deciding factor but one might be ideal for your organization over another.
* Web services have a lot of competition with each other. Finding the one that fits your organizational needs best is likely the best pick. Whether that's self-hosting with Render, database usage like Aiven, or one with cloud capabilities like AWS.
# Summary:
* My suggestion for our project is to utilize docker to build an image of the backend and upload it to Render. We need to do it that way rather than directly from Github due to privacy control of the repository.
 Using Aiven to host the database is perfect for our project and it runs MySql which is how we are building the database. Having these both hosted online allows us all to be able to utilize the same system and not
 have bugs localized to our own builds. The downside is updating the backend is not as easy as a simple save and run like you could do hosted on a personal computer. We already have Flutter for the front end and it
 works perfectly with connecting to both Render and Aiven. This set-up will work for all three sides of FE-BE-DB. 
# References:
    1. ChatGpt
    2. Wikipedia
    3. Amazon Web Services
    4. Educative.IO
    5. Google Copilot
