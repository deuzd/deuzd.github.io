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


RPG Map is a project that I did back in high school for my AP Computer Science class. This was an individual project where we had to create a map with barriers, almost like a maze. The main goal of the game was simply to get from the spawn point of the maze to the end. However there are enemies along the way in which you will have to defeat in order to continue your game.

When you first start, you will also be allowed to choose a character and name them. There are different characters which all sport different spreads of stats such as varying amounts of health and damage output, akin to most RPG's having such roles like "tank", "mage", or "knight".

When you encounter enemies you will be put into a auto battle of sorts where you essentially fight until you either defeat the enemy or lose all you health points. Throughout the maze and sometimes after defeating enemies you can pick up items that do things such as heal you or increase your damage output for the next fight, helping you increase your chances of survival.

Here are some examples of the Java classes used to create the game:

## Game runner class
```java
//Import a scanner for user interaction
import java.util.Scanner;
//Main class that will deal with the game being played
public class GameRunner {
    //Main method to be run that will allow for the map to change and the characters to win or lose
    public static void main(String[] args) {
        //Creating variable to be used later and placing the initial player, enemy, and item
        Scanner scan = new Scanner(System.in);
        Map gameRoom = new Map("room1");
        Character player = new Character(2, 2, 40, 40);
        Enemy enemy = new Enemy(4, 1, 30, 10);
        Item atkPot = new Item(1,1);
        gameRoom.placeObject(player);
        gameRoom.placeObject(enemy);
        gameRoom.placeObject(atkPot);

        System.out.println("What direction do you want to go? use WASD");
        String input = scan.next();
        boolean valid = false;
        int wins = 0;
        int counter = 0;

        //While loop that will keep the game going as long as you don't run into a wall, or invalid input
        while (!input.equalsIgnoreCase("X")) {
            player.move(input, gameRoom);
            //Checking to see if the item can be obtained by the player
            if(gameRoom.itemInRange(player, atkPot)){
                //If statement so the saying only repeats once and not continuously since the condition will always be true
                if(counter == 0) {
                    System.out.println(TEXT_RED + "YOUR STRENGTH POTION WILL INCREASE \nYOUR ATTACK OVER TIME" + TEXT_RESET);
                }
                counter++;
                player.setAttack(player.getAttack() + 1);
                gameRoom.removeObject(atkPot);
            }
            //Checking to see if the player can now attack the enemy on the board (either one vertical or horizontal of the player
            if (gameRoom.enemyInRange(player, enemy)) {
                System.out.println(TEXT_PURPLE + "Roses are red, \nViolets are blue, \nThere is an enemy nearby, \nAnd they're coming for you :) \n" + TEXT_RESET);
                Scanner opt = new Scanner(System.in);
                System.out.println(player);
                System.out.println(enemy);
                System.out.println("\nWhat do you want to do? \n1) Fight \n2) Give up");
                //Move sequence that will keep going until one character dies
                while (player.getHealth() > 0 && enemy.getHealth() > 0 && !valid) {
                    int choice = Integer.parseInt(opt.next());
                    //Asking what the player wants to do
                    if (choice == 1) {
                        //Attack sequence that will keep going until one character dies
                        while (player.getHealth() > 0 && enemy.getHealth() > 0) {
                            player.attackOpp(enemy);
                            enemy.attackPlay(player);
                        }
                        //Condition if you or your opponent dies, though if you win then you will go onto the next level after beating the required enemies
                        if (player.getHealth() == 0) {
                            System.out.println(TEXT_CYAN + "YOU LOST :( \nGame over" + TEXT_RESET);
                        } else if (enemy.getHealth() == 0) {
                            System.out.println(TEXT_CYAN + "YOU WIN :)" + TEXT_RESET);
                            //If you still have enemies to beat you heal after each victory
                            if (wins < 2) {
                                System.out.println(TEXT_BLUE + "YOU HAVE HEALED 20HP AFTER YOUR WIN" + TEXT_RESET);
                                player.setHealth(player.getHealth() + 20);
                            }
                            gameRoom.removeObject(enemy);
                            wins++;
                            //If you still have enemies to beat you will keep on moving
                            if (wins < 3) {
                                System.out.println("What direction do you want to go? use WASD");
                            }
                            //Creating the locations of the new enemies
                            if (wins == 1) {
                                enemy = new Enemy(1, 5, 40, 10);
                                enemy.setHealth(50);
                                gameRoom.placeObject(enemy);
                            } else if (wins == 2) {
                                enemy = new Enemy(5, 5, 40, 10);
                                enemy.setHealth(50);
                                gameRoom.placeObject(enemy);
                            }else{
                                System.out.println(TEXT_GREEN + "YOU WILL NOW GO ON TO THE NEXT LEVEL" + TEXT_RESET);
                                System.out.println(TEXT_BLUE + "YOU HAVE HEALED FOR AN ADDITIONAL 20HP" + TEXT_RESET);
                                scan = new Scanner(System.in);
                                gameRoom = new Map("room2");
                                player = new Character(2, 2, 40, 40);
                                enemy = new Enemy(4, 5, 40, 10);
                                atkPot = new Item(8,8);
                                gameRoom.placeObject(player);
                                gameRoom.placeObject(enemy);
                                gameRoom.placeObject(atkPot);
                                player.setHealth(player.getHealth() + 20);
                                System.out.println("What direction do you want to go? use WASD");
                                input = scan.next();
                                wins = 0;
                                counter = 0;
                                //While loop that will keep the game going as long as you don't run into a wall, or invalid input
                                while (!input.equalsIgnoreCase("X")) {
                                    player.move(input, gameRoom);
                                    //Checking to see if the item can be obtained by the player
                                    if(gameRoom.itemInRange(player, atkPot)){
                                        //If statement so the saying only repeats once and not continuously since the condition will always be true
                                        if(counter == 0){
                                            System.out.println(TEXT_RED + "YOUR STRENGTH POTION WILL INCREASE \nYOUR ATTACK OVER TIME" + TEXT_RESET);
                                        }
                                        counter++;
                                        player.setAttack(player.getAttack() + 1);
                                        gameRoom.removeObject(atkPot);
                                    }
                                    //Checking to see if the player can now attack the enemy on the board (either one vertical or horizontal of the player
                                    if (gameRoom.enemyInRange(player, enemy)) {
                                        System.out.println(TEXT_PURPLE + "Roses are red, \nViolets are blue, \nThere is an enemy nearby, \nAnd they're coming for you :) \n" + TEXT_RESET);
                                        opt = new Scanner(System.in);
                                        System.out.println(player);
                                        System.out.println(enemy);
                                        System.out.println("\nWhat do you want to do? \n1) Fight \n2) Give up");
                                        //Move sequence that will keep going until one character dies
                                        while (player.getHealth() > 0 && enemy.getHealth() > 0 && !valid) {
                                            choice = Integer.parseInt(opt.next());
                                            //Asking what the player wants to do
                                            if (choice == 1) {
                                                //Attack sequence that will keep going until one character dies
                                                while (player.getHealth() > 0 && enemy.getHealth() > 0) {
                                                    player.attackOpp(enemy);
                                                    enemy.attackPlay(player);
                                                }
                                                //Condition if you or your opponent dies, though if you win then you will go onto the next level after beating the required enemies
                                                if (player.getHealth() == 0) {
                                                    System.out.println(TEXT_CYAN + "YOU LOST :( \nGame over" + TEXT_RESET);
                                                } else if (enemy.getHealth() == 0) {
                                                    System.out.println(TEXT_CYAN + "YOU'VE WON THE GAME CONGRATULATIONS :)" + TEXT_RESET);
                                                    //If you still have enemies to beat you heal after each victory
                                                    if (wins < 2) {
                                                        System.out.println(TEXT_BLUE + "YOU HAVE HEALED 20HP AFTER YOUR WIN" + TEXT_RESET);
                                                        player.setHealth(player.getHealth() + 20);
                                                    }
                                                    gameRoom.removeObject(enemy);
                                                    wins++;
                                                    //Creating the locations of the new enemies
                                                    if (wins == 1) {
                                                        enemy = new Enemy(7, 1, 40, 10);
                                                        enemy.setHealth(50);
                                                        gameRoom.placeObject(enemy);
                                                    } else if (wins == 2) {
                                                        enemy = new Enemy(1, 1, 40, 10);
                                                        enemy.setHealth(50);
                                                        gameRoom.placeObject(enemy);
                                                    }
                                                    //If you still have enemies to beat you will keep on moving
                                                    if (wins < 3) {
                                                        System.out.println("What direction do you want to go? use WASD");
                                                    }
                                                    break;
                                                }
                                            } else if (choice == 2) {
                                                System.out.println("You lose :(");
                                                valid = true;
                                                break;
                                            } else {
                                                System.out.println("You can't do that!");
                                            }
                                        }


                                    } else {
                                        System.out.println("What direction do you want to go? use WASD");
                                    }
                                    input = scan.next();
                                }
                            }

                            break;
                        }
                    } else if (choice == 2) {
                        System.out.println("You lose :(");
                        valid = true;
                        break;
                    } else {
                        System.out.println("You can't do that!");
                    }
                }


            } else {
                System.out.println("What direction do you want to go? use WASD");
            }
            input = scan.next();
        }
    }
    //To change the colors of the text
        public static final String TEXT_RESET = "\u001B[0m";
        public static final String TEXT_CYAN = "\u001B[36m";
        public static final String TEXT_PURPLE = "\u001B[35m";
        public static final String TEXT_BLUE = "\u001B[34m";
        public static final String TEXT_GREEN = "\u001B[32m";
        public static final String TEXT_RED = "\u001B[31m";
    }

```
## Map class
```java
//What will print to the console when showing the map
public class Map {
   //Making a private variable to change later on
    private Mappable[][] board;

    //Creating the map from the text file by turning it inot a string
    public Map(String file){
        MediaFile.setInputFile(file);
        String info = MediaFile.readString();
        int row = Integer.valueOf(info.substring(0,info.indexOf(" ")));
        int column = Integer.valueOf(info.substring(info.indexOf(" ") + 1));
        board = new Mappable[row][column];

        //For loop that will make each row of the map based off of the text file, using the regex to tell values apart
        for(int r = 0; r < board.length; r++) {
            info = MediaFile.readString();
            String[] line = info.split(" ");
            //Creating the columns that will map up the rest of the map
            for(int c = 0; c < board[r].length; c++){
                //Setting it so that it will read the text and create walls that the player may not go out of bounds
                if(line[c].equals("1")){
                    board[r][c] = new Wall(r, c);
                }
            }
        }
    }

    //Method in order to place the obeject on the map to later be moved or taken off; may also be used to initially place something
    public void placeObject(Mappable toPlace){
        board[toPlace.getCurrRow()][toPlace.getCurrCol()] = toPlace;
        printMap();
    }

    //Method that removes an object from the map by turning it into null (no value)
    public void removeObject(Mappable toRemove){
        board[toRemove.getCurrRow()][toRemove.getCurrCol()] = null;
    }

    //Checking to see if the player may go out of bounds and to take direction to move
    public boolean canMove(int row, int col){
        //Just in case the movement command isn't valid
        if(board[row][col] != null){
            return false;
        }else if(row < 0 || row >= board.length){
            return false;
        }else if(col < 0 || col >= board.length){
            return false;
        }
        return true;
    }

    //Checking to see if the enemy is in attacking range
    public boolean enemyInRange(Character c, Enemy e){
        //If they are the method will return true and allow the player to attack the enemy in GameRunner
        if(board[c.getCurrRow()][c.getCurrCol() - 1] == board[e.getCurrRow()][e.getCurrCol()]){
            return true;
        }else if(board[c.getCurrRow()][c.getCurrCol() + 1] == board[e.getCurrRow()][e.getCurrCol()]){
            return true;
        }else if(board[c.getCurrRow() - 1][c.getCurrCol()] == board[e.getCurrRow()][e.getCurrCol()]){
            return true;
        }else if(board[c.getCurrRow() + 1][c.getCurrCol()] == board[e.getCurrRow()][e.getCurrCol()]){
            return true;
        }else{
            return false;
        }
    }

    //Essentially the same as enemy, but the parameter will accept an item instead to tell the difference so you can't attack it
    public boolean itemInRange(Character c, Item i){
        //If they are the method will return true and allow the player to pick up the item in GameRunner
        if(board[c.getCurrRow()][c.getCurrCol() - 1] == board[i.getCurrRow()][i.getCurrCol()]){
            return true;
        }else if(board[c.getCurrRow()][c.getCurrCol() + 1] == board[i.getCurrRow()][i.getCurrCol()]){
            return true;
        }else if(board[c.getCurrRow() - 1][c.getCurrCol()] == board[i.getCurrRow()][i.getCurrCol()]){
            return true;
        }else if(board[c.getCurrRow() + 1][c.getCurrCol()] == board[i.getCurrRow()][i.getCurrCol()]){
            return true;
        }else{
            return false;
        }
    }

    //Printing the map each time called since the pieces of the game may be moving
    public void printMap(){
        //Enhanced for loop that will create the new board to print
        for(Mappable[] row : board){
           for(Mappable x : row){
               if(x != null){
                   System.out.print(" " + x.getSymbol());
               }else{
                   System.out.print("  ");
               }
           }
           System.out.println();
        }
    }
}
```
## Example of a character class
```java
//Creating the character you will play as that takes info from mappable
public class Character extends Mappable{
    //Private variables that can be referenced throughout the class
    private int attack;
    private int defense;
    private int health;

    //Creating constructors, getters, and setters to declare an actual value in the map and the stats, call for the symbol, and get/set the stats of an object
    public Character(int r, int c, int atk, int def){
        super(r, c);
        attack = atk;
        defense = def;
        health = 50;
    }
    public int getHealth(){
        return health;
    }
    public void setAttack(int a){
        this.attack = a;
    }
    public int getAttack() {
        return attack;
    }
    public int getDefense() {
        return defense;
    }
    public void setHealth(int health) {
        this.health = health;
    }
    public String getSymbol(){
        return "C";
    }

    //Allows for the character to move within the map by asking where it wants to go and deleting the image afterwards so there is no afterimage
    public void move(String direction, Map room){
        room.removeObject(this);
        //Based on which key is pressed, the character will move in that direction
        if(direction.equals("w")){
            //Checks if the character can actually move to that space or if it is inhibited by a wall
            if(room.canMove(this.getCurrRow() - 1, this.getCurrCol())){
                this.setCurrRow(this.getCurrRow() - 1);
            }
        }else if(direction.equals("a")){
            if(room.canMove(this.getCurrRow(), this.getCurrCol() - 1)){
                this.setCurrCol(this.getCurrCol() - 1);
            }
        }else if(direction.equals("s")){
            if(room.canMove(this.getCurrRow() + 1, this.getCurrCol())){
                this.setCurrRow(this.getCurrRow() + 1);
            }
        }else if(direction.equals("d")){
            if(room.canMove(this.getCurrRow(), this.getCurrCol() + 1)){
                this.setCurrCol(this.getCurrCol() + 1);
            }
        }
        room.placeObject(this);
    }

    //Attack method used when attacking the enemy
    public void attackOpp(Enemy opp){
        int attack = (int)(Math.random() * 40 + 1);
        int block = (int)(Math.random() * opp.getDefense() + 1);
        int difference = attack - block;
        //Changing the values so that if the total damage is negative, the attack is "neutralized
        if(difference < 0){
            difference = 0;
        }
        System.out.println("\n" + "You are attacking for: " + attack);
        System.out.println("Your opponent is blocking for: " + block);
        opp.setHealth(opp.getHealth() - difference);
        //If the opponent dies, then their health will just be set to 0
        if(opp.getHealth() < 0){
            opp.setHealth(0);
        }
        System.out.println("They have " + opp.getHealth() + " health left");
        System.out.println();
        System.out.println("----------------------------------------");
    }

    //toString method to print out the characters stats
    public String toString(){
        return "YOUR ATTACK: " + attack + "\nYOUR DEFENSE: " + defense + "\nYOUR HEALTH: " + health;
    }
}

```

