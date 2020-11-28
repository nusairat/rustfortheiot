# Rust for the IOT - Application

![Rust IOT](/assets/book.jpg)

This repository is the accompanying code and full example application for the Apress book [Rust for the IOT](https://www.apress.com/us/book/9781484258590). The code in the first chapter mostly goes over examples in Rust and how to learn Rust. The rest of the book is divided into two sections the backend microservices and the Raspberry Pi. Throughout the book we will build upon the code often circling back to services and even functions. 

## Installation

Since this is a rust book at minimum you will need to install Rust, we will also will rely heavily on Docker as well. The book goes into more detail at the times needed to install.

### Feature Flags

Because we build up the code throughout the book, I didn't want to deploy a new set of code for each chapter, it becomes very hard to maintain and hard on the user. So for the book I rely on feature flags for functions and blocks of code that get built up upon and are different from one chapter to next.

## Sections

The following are the different code blocks.

### Backend Microservices
- [MQ Service Handler](mqtt_service/)
- [Retrieval Service](retrieval_svc/)
- [Upload Service](upload_svc/)

### Raspberry Pi Service
- [Auth Library](rasp-auth/)
- [Raspberry Pi Main Application](rasp-pi-app-master/)
- [Raspberry Pi MQ Handler](rasp-pi-mq/)

## TODO

While this application is fully running, there are a few things I would want to update. And will in the future

1. The code to record the meta data is correct, but won't compile on the docker image right now. I need to get the correct libraries installed.

2. I update libraries as I can; however, some libraries would require quite a bit of code changes to do. I haven't decided but may branch off later to do that. Eventstore specifically, has been updated quiet a bit last year, I had to update it right before the book was published and has already changed.

## Problems

Books are quite a bit of work, especially one like this that uses servers, hardware, and a multitude of libraries. If you have any questions or problems you can ping me on twitter @nusairat or write an issue and I can try to address it.