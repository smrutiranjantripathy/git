#**Cracking the Git Version Control System**

##What is Git ?
Git is the most widely used version controls system by developers community. As a distributed revision control system it is aimed at speed, data integrity, and support for distributed, non-linear workflows.As with most other distributed version control systems, and unlike most client–server systems, every Git directory on every computer is a full-fledged repository with complete history and full version-tracking capabilities, independent of network access or a central server

## Git Brief History
Git was developed by Linus Trovalds for managing the linux source code.Earlier in 1998 before *Git*  *Bitkeeper* was considered as a solution for managing the linux source code. Bitkeeper used to provide access to the system for certain open source or free software projects, one of which was the source code of the Linux kernel. The license for the "community" version of BitKeeper had allowed for developers to use the tool at no cost for open source or free software projects, provided those developers did not participate in the development of a competing tool (such as Concurrent Versions System, GNU Arch, Subversion or ClearCase) for the duration of their usage of BitKeeper plus one year. This restriction applied regardless of whether the competing tool was free or proprietary. The decision made in 2002 to use BitKeeper for Linux kernel development was a controversial one.But this decision was not suipported by some developers becuase of the licensing clauses. They believed the project was ceding some control to a proprietary developer.In 2005 Bitmover removed the free version to all the OSDL employess including Linus Trovalds because of a client developed by one of the OSDL employee Andrew Tridgell which mimics one of the core features of version control system provided by Bitkeep.It lead to the need of the development of a version control system which could match the needs of the linux project. 


##Installation 
**For Redhat or cent-os like systems**:
```sudo yum install git-all```

**For debian-based distribution systems like Ubuntu**:
```sudo apt-get install git-all```

##Minimal Configuration
* User's Name
```git config --global user.name "Your Name"```
* User's Email
```git config --global user.email "name@example.com"```
* To check global configuration
```git config --global --list
          or
   git config --global -e```
























