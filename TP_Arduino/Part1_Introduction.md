x# MIF18 : Scheduling on Arduino -- Prise en main

  * Grégoire Pichon, Université Lyon 1, LIP [email](mailto:gregoire.pichon@univ-lyon1.fr)
  * Version: 2022
  * Auteur original: Laure Gonnord
  * Inspiré d'un TP de Julien Forget et Thomas Vantroys, Lille
  * Autre collaborateur: Thierry Excoffier (Lyon1).

## Description

Dans ce TP d'introduction, vous écrirez des programmes pour Arduino qui permettent d'intéragir avec des capteurs. L'objectif est double:
* Manipuler la plateforme et la chaine de compilation
* Expétimenter deux variantes de programmation Arduino et les comparer (si vous avez le temps)

Pré-requis : Testez votre [setting](_startup_part1.md) Arduino

## Step 1:  Led sur Digital 13 + Bouton sur Digital 10 (_code/ex1/)

* Bouton sur digital 10, avec une résistance 220 ohm

![Bouton sur Port Digital 10](figs/p-boutonpoussoir_arduino.png)

*  Ecrivez une fonction `int get_button_state()` qui lit sur le port digital 10 (en utilisant `PINB` value et des opérateurs booléens). Appelez cette fonction dans le `main` pour controler la LED (la switcher d'on a off ou l'inverse si le bouton est pressé).

## Step 2: Deux LEDs avec des fréquences différentes (_code/ex2/)

Maintenant vous allez faire clignoter deux LEDs avec des fréquences différentes. Utiliser le PIN 12 pour la seconde LED. Essayez d'avoir un code aussi générique que possible.

Comment se comporte votre solution avec différentes valeurs de fréquences ? Est-ce suffisant ?

## Step 3: Led, Bouton (_code/ex3/) -- seulement si vous avez le temps (chez vous par ex.)

### L'exemple de la LED
* Incluez le fichier `Arduino.h` et faite le linkage avec la lib (le Makefile le fait pour vous):
```C
#include <avr/io.h>
#include <util/delay.h>
#include <Arduino.h>
```

* Désormais, chaque pin a sa propre configuration et peut être configurée indépendamment des autres: `pinMode(led, OUTPUT);` pour activer la LED
`digitalWrite(led, LOW);`,  `digitalWrite(led, HIGH);` pour changer la valeur de la LED.

* Vous devez stocker la value actuelle de la LED dans la variable `led_on`.

* [The Arduino C++ library reference](https://www.arduino.cc/en/Reference/HomePage). Vous pouvez regarder la documentation pour `pinMode` et `digitalRead`.

### Expected Work

* Implementez la fonctionnalité de gestion du Bouton et testez là.

* A qui se destine ce language ?