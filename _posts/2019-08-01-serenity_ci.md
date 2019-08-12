---
title:  "Dependency Injection in Serenity"
comments: true
updated: 2019-08-01 15:56
---
# Wstęp

W artykule tym będę opowiadał o bibliotece [Serenity BDD](http://). Skupię się na mechanizmie dependency injection wbudowanym w tą bibliotekę. W części praktycznej opiszę jak dobrze urzyć tego mechanizmu w testach automatycznych aby kod był przyjemniejszy do pracy. 

# Czym jest dependency injection?



Serenity has very simple to use implementation of Dependency Injections (DI).

Directive @Step is a DI tag.

Every object created usin @Step is created automaticaly by Serenity, using default constructor, and then injected into your class.

