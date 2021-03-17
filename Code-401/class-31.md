# Class 31: Django REST Framework & Docker

## [Beginner’s Guide to Docker](https://wsvincent.com/beginners-guide-to-docker/)

**With Docker it doesn’t matter if you are using a Mac, Windows, or Linux computer anymore. The entire development environment is isolated: programming language, software packages, databases, and more.**

> No longer need to run a virtual environment and it can be shared with others to ensure that they have the same environment

## Linux Containers

Docker is really just Linux containers which are a type of [virtualization](https://en.wikipedia.org/wiki/Virtualization).


> Programmers used to use [virtual machines](https://en.wikipedia.org/wiki/Virtual_machine) to perform their work on one shared machine. Virtual machines are complete copies of a computer from the OS up.


A typical guest operating system can easily take up 700MB of size. So if one physical server supports three virtual machines, that’s at least 2.1GB of disk space taken up along with separate needs for CPU and memory resources.

Fundamentally, Docker is a way to implement Linux containers!

> An analogy we can use here is that of homes and apartments. Virtual Machines are like homes: stand-alone buildings with their own infrastructure including plumbing and heating, as well as a kitchen, bathrooms, bedrooms, and so on. Docker containers are like apartments: they share common infrastructure like plumbing and heating, but come in various sizes that match the exact needs of an owner.

## Containers vs. Virtual Environments

Virtual environments are used to isolate Python software packages locally. We can create an isolated box for individual projects so one can use Python 2.7 and Django 1.5 while another can use Python 3.5 and Django 2.1 on the same computer. 

Virtual environments can only isolate Python packages. They still rely on a global, system-level installation of Python however, they can refer to the proper version.

## Install Docker

Install Docker, [download the desktop app on your computer and create a free account](https://www.docker.com/get-started).

Once complete, confirm your install:

```
$ docker --version
Docker version 19.03.5, build 633a0ea
```














## [Django for APIs - Library Website](https://djangoforapis.com/library-website-and-api/)



## [Beginner’s Guide to Django REST Framework](https://wsvincent.com/official-django-rest-framework-tutorial-beginners-guide/)