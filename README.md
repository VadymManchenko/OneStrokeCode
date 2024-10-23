# Project Documentation

## Overview

This project was developed for the **Robot_Dreams competition** and serves as a digital expression of solidarity with Ukraine during its ongoing struggle against aggression. The core functionality of the program is to display a message along with its translations into various languages, emphasizing global support for Ukraine.

## Problem statement

In light of the current geopolitical climate, there is a pressing need to raise awareness and support for Ukraine. This program aims to use technology to convey a powerful message, fostering unity and resilience among supporters worldwide.

## Features

- Asynchronous message display
- Multilingual translations of a critical phrase
- Visual representation of solidarity with Ukraine

## Code explanation

The code consists of a single asynchronous function that:

1. Initializes a `putin` object with a message.
2. Prepares an array of translations in multiple languages.
3. Defines a delay function to control the timing of message display.
4. Iterates through the translations, displaying each one sequentially with a typing effect.
5. Prints "Слава Україні!" at the end to affirm support.

## Code compiliing 

The program was compiled and executed using the online JavaScript compiler available at [Programiz](https://www.programiz.com/javascript/online-compiler/).
!(/image.png "Виконання програми")


### Code snippet

```javascript
let putin = {message: "йди за руським кораблем"},
    translations = ["go by russian warship", "va avec le navire de guerre russe", "geh mit dem russischen Kriegsschiff", "ロシアの軍艦を追いかける", "vai con la nave da guerra russa"],
    delay = (ms) => new Promise(r => setTimeout(r, ms)),
    printMessage = async msg => { 
        for (let i = 0; i < msg.length; i++) { 
            process.stdout.write(msg[i]); 
            await delay(50); 
        } 
        console.log(""); 
    };

(async () => { 
    for (let i = 0; i < translations.length + 1; i++) { 
        await delay(i * 1500); 
        await printMessage(`${i + 1}. putin : ${i === 0 ? putin.message : translations[i - 1]}`); 
    } 
    console.log("Слава Україні!"); 
})();