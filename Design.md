[[_TOC_]]

# Design
This document outlines the design of the features, requirements, and use cases as listed in Milestone 1 (Requirements).

# Updated Project Description

### What is Word Flow?

Word Flow is an application to train users to type faster and with greater accuracy. The focus is on unique uses not covered by other typing tools- special characters used by programming languages, and typing from audio content. Word flow is designed to be used within classrooms and schools, and thus includes a hierarchical user management structure, based on a School with Classrooms. This software can be deployed to a School System, and the School can be in charge of inviting and managing their own students.

Main functionality includes:

* Users can complete a variety of typing challenges and view their speed and accuracy for each challenge and see how they have improved over time.
* Admin users can create Classrooms of users, assign them challenges to complete, and view reports for these users.
* Super Admin users can create a School, invite users to join, and assign classrooms to be managed by Admins.

The typing challenges will range from standard English words, to specific programming languages, and typing from audio dictation. It can check the user's input text against the challenge text, showing the user where they are in the text and if they have made any errors, and how much time is remaining for the challenge. Once complete, they will see their speed and accuracy within the challenge.

The application is designed for desktop environments and created in the Python programming language. It utilizes the Firebase API for user authentication and database management. Users can access their account information from different computers. Text content is stored in an external database. Audio content for dictation mode is generated from database text via text-to-speech.

# Storyboards

Below are our storyboards which outline the ways in which users can interact with Word Flow's functionality.

[Design Storyboards](/Design/Design-Storyboards)

# System Architecture Details and Domain Model

Below is the domain model and an explanation of the architectures we chose and why we chose them.

[System Architecture Details and Domain Model](/Design/System-Architecture-Details-and-Domain-Model)

# Interaction Diagrams

Below are interaction diagrams.

[Interaction Diagrams](/Design/Interaction-Diagrams)

# Persistent Storage Details

Below are persistent Storage Details.

[Persistent Storage Details](/Design/Persistent-Storage-Details)