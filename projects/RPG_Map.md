---
layout: project
type: project
image: img/micromouse/micromouse-square.jpg
title: "RPG_Map"
date: 2022-04-15
published: true
labels:
  - Game
  - Java
summary: "RPG Map is a project I did in high school where we had to create a game where you essentially are playing a basic form of an RPG."
---

<div class="text-center p-4">
  <img width="200px" src="../img/micromouse/micromouse-robot.png" class="img-thumbnail" >
  <img width="200px" src="../img/micromouse/micromouse-robot-2.jpg" class="img-thumbnail" >
  <img width="200px" src="../img/micromouse/micromouse-circuit.png" class="img-thumbnail" >
</div>

RPG Map is a project that I did back in high school for my AP Computer Science class. This was an individual project where we had to create a map with barriers, almost like a maze. The main goal of the game was simply to get from the spawn point of the maze to the end. However there are enemies along the way in which you will have to defeat in order to continue your game.

When you first start, you will also be allowed to choose a character and name them. There are different characters which all sport different spreads of stats such as varying amounts of health and damage output, akin to most RPG's having such roles like "tank", "mage", or "knight".

When you encounter enemies you will be put into a auto battle of sorts where you essentially fight until you either defeat the enemy or lose all you health points. Throughout the maze and sometimes after defeating enemies you can pick up items that do things such as heal you or increase your damage output for the next fight, helping you increase your chances of survival.

```cpp
byte ADCRead(byte ch)
{
    word value;
    ADC1SC1 = ch;
    while (ADC1SC1_COCO != 1)
    {   // wait until ADC conversion is completed   
    }
    return ADC1RL;  // lower 8-bit value out of 10-bit data from the ADC
}
```

You can learn more at the [UH Micromouse News Announcement](https://manoa.hawaii.edu/news/article.php?aId=2857).
