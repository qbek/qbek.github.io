---
title:  "Dependency Injection in Serenity"
comments: true
updated: 2019-08-01 15:56
---

Serenity has very simple to use implementation of Dependency Injections (DI).

Directive @Step is a DI tag.

Every object created usin @Step is created automaticaly by Serenity, using default constructor, and then injected into your class.

