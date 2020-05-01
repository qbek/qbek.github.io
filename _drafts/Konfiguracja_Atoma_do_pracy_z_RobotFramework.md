---
layout: post
title: Konfiguracja Atom'a do pracy z&nbspRobotFramework
category: narzędzia
tags: robotframework
comments: true
---


## Edytor Atom

Jeżeli znasz to nie muszę Cię zachęcać. Jeżeli nie znasz i piszesz testy w RobotFramework'u, spróbuj koniecznie. Do pobrania, całkowicie za darmo, z [oficjalnej strony](http://atom.io)

Największymi zaletami tego edytora jest jego szybkość i bardzo bogata biblioteka dodatków, która pozwala z niego zrobić znakomite narzędzie deweloperskie do większości technologi. Sam przez długi czas korzystałem z pyCharam'a, ale jak to mawiają *"Umarł król, niech żyje król"*.

Poniżej znajdziesz listę dodatków, które warto sobie dodać do Atom'a, które znacząco umilają pracę.

## Autocomplete

Podpowiadanie dostępnych funkcji potrafi bardzo przyśpieszyć pracę z kodem. Zaczynasz pisać a Atom podsuwa Ci listę dostępnych keywordów.

![Hyperclick w akcji]({{ site.url }}/assets/autocompletion.gif)

Działa zarówno w przypadku bibliotek, jak i keywordów stworzonych przez Ciebie. Musisz zainstalować dodatki:

[language-robot-framework](https://atom.io/packages/language-robot-framework) - wsparcie dla składni RobotFramework. Dodaje przydatne snippety, np. wpisz `*k` a następnie naciśnij `Tab` a otrzymasz `*** Keywords ***`
* `*s` -> `*** Settings ***`
* `*v` -> `*** Variables ***`
* `*t` -> `*** Test Cases ***`
* `*k` -> `*** Keywords ***`

[autocomplete-robot-framework](https://atom.io/packages/autocomplete-robot-framework) - jak sama nazwa wskazuje, dodaje uzupełnianie składni. Przykład działania jest dobrze pokazany na stronie dodatku.

Oba pakiety możesz szybko zainstalować z poziomy konsoli / terminala:
```
apm install language-robot-framework
apm install autocomplete-robot-framework
```


## Skok do definicji keyworda

Przydatna funkcjonalność pozwalająca na szybkie przejście do definicji keyworda, którego napisałeś/-aś. Funkcja tym bardziej przydatna im więcej kodu już jest napisane. Najedź kursorem na keyworda, a następnie `ctrl + click` (`cmd + click` na osx), a Atom automatycznie przekieruje Cię do jego definicji:

![Hyperclick w akcji]({{ site.url }}/assets/goto_keyword.gif)

Zainstaluj następujące dodatki:

[hyperclick](https://atom.io/packages/hyperclick) - główny silnik opisywanej funckjonalności, można go rozszerzać o wsparcie dla wielu języków poprzez dodatkowe wtyczki

[hyperclick-robot-framework](https://atom.io/packages/hyperclick-robot-framework) - wsparcie dla RobotFramework

Instalacja z poziomu konsoli / terminala:
```
apm install hyperclick
apm install hyperclick-robot-framework
```


## Uruchamianie testów z poziomu Atom'a

```
apm install atom-shell-commands
```




Wymagana konfiguracja komend dla pluginu

```cson
"*":
  "atom-shell-commands":
    commandsList: [
      {
        name: "Run single test"
        command: "robot"
        arguments: [
          "--test"
          "{CurLineText}"
          "{FileName}"
        ]
        options:
          cwd: "{FileDir}"
      }
      {
        name: "Run file tests"
        command: "robot"
        arguments: [
          "{FileName}"
        ]
        options:
          cwd: "{FileDir}"
      }
    ]
  //reszta konfiguracji Atom

```

![Hyperclick w akcji]({{ site.url }}/assets/test_execution.gif)

![Hyperclick w akcji]({{ site.url }}/assets/file_test_execution.gif)
