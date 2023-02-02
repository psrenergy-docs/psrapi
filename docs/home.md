---
layout: default
title: Home
nav_order: 1
description: "PSR's API for case management and model execution"
permalink: /
---

# What is the API?

* It is a dll (a .NET dynamic library) that you can integrate directly into your system
* Main objectives:
  * case management
  * control the execution flow
  * run multiple cases and modify (in real time) case data
  * Abstraction of our database files format
* Communication language is heavily based on JSON syntax
* Provided in two options:
  * standalone application that works as an http service
  * windows service application
* Instead of using the DLL functions directly (you can make HTTP requests to this top layer)

> **Warning**
> Still in “alpha” state
> Still improving/still stabilizing/still not representing everything

# What the API can’t do:
* Create/populate an entire database from scratch
* Create new entities not initially contained in the original base
* Physical deletion of entities

# Support or Contact

Having trouble? Contact our support team via `sddp@psr-inc.com` and we’ll help you sort it out.

