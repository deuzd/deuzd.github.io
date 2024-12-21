---
layout: project
type: project
image: img/cotton/connect_four.png
title: "Connect_Four"
date: 2022-02-08
published: true
labels:
  - Game
  - Java
summary: "A simple connect four game that can print out a map and has the player choose where they want to place their piece. This game can be two player with alternating turns which is the same as the physical game."
---

In this project I did in high school we made a simple connect for game. The players will alternate turn and choose a column to drop their piece in. The piece will "fall" until it hits a piece that was alread dropped or the bottom of the frame of the game, being the "bottom". It will constantly look for a winner, being able to read if there is four of a kind in any row, column, or diagonal.

## ConnectFour class to place pieces
```java
public class ConnectFour {

    /* The ConnectFour board will be a 2D array of ints where
     * a value of 0 means the space is EMPTY
     * a value of 1 means the space has a RED chip
     * a value of 2 means the space has a BLACK chip
     */
    private int[][] board;

    /* The constructor that initializes the board to the
     * # of ROWS and COLS
     */
    public ConnectFour() {
        board = new int[Game.ROWS][Game.COLS];
    }


    /**
     * This method should place a chip for the current player by "dropping" the chip to the
     * "lowest" possible spot in the specified column.  Keep in mind that visually, the top left
     * corner of the grid is row = 0 and column = 0.
     * Note, this method does NOT have to keep track of which player's turn it is.
     * @param column represents the selected by the player. If the player wants the 1st column,
     *               this parameter will have a value of 1, but that corresponds to an index value of 0.
     * @param player represents the current player.  The value will either be RED (1) or BLACK (2).
     */
    public void placeChip(int column, int player) {
        //Int to simplify what column as when called it goes to the value of 1 before the number input
        int c = column - 1;
        //For loop that will run through the 2D array and will place a "chip" at the earliest instance at which teh spot is empty within the column the player selected
        for(int i = getBoardCopy().length - 1; i > -1; i--){
            //If statement that checks if the spot is empty and if it is it will place a chip and end the loop, otherwise it will continue the for loop
            if(board[i][c] == 0){
                board[i][c] = player;
                break;
            }
        }
        //Calling the isFull method to stop the game if the column selected is already full
        isFull(column);
    }

    /**
     * If a column is full, you should not be able to add another chip into that column.
     * This method should keep help determine whether there is space in the specified column.
     * Depending on your placeChip() method, you may not need to write change this code.
     * @param selection represents the column the player has selected
     * @return true if the column is already full,  otherwise return false
     */
    public boolean isFull(int selection) {
        //Will return true if the column is full by checking the array to see if the top spot of that column already has a value and therefore a chip placed there, otherwise return false and let the game continue
        return board[0][selection - 1] != 0;
    }

    /**
     * This method looks for four in a row in a column or a row.
     * For example .---.---.---.---.      .---.---.---.---.
     *             | X |   |   |   |      |   |   |   |   |
     *             .---.---.---.---.      .---.---.---.---.
     *             | X |   |   |   |      | X | X | X | X |
     *             .---.---.---.---.  OR  .---.---.---.---.
     *             | X |   |   |   |      |   |   |   |   |
     *             .---.---.---.---.      .---.---.---.---.
     *             | X |   |   |   |      |   |   |   |   |
     *             .---.---.---.---.      .---.---.---.---.
     * @param player represents the current player.  The value will either be RED (1) or BLACK (2).
     * @return true if four in a row can be found in either orientation, otherwise false.
     */
    private boolean checkRows(int player) {
        //For loop that runs through each row, starting from the bottom working its way up
        for(int r = board.length - 1; r != -1; r--){
            //Secondary for loop to run through each column spot in said row and will act as the second number at which it will be checked for the starting spot
            for(int c = 0; c < board.length - 3; c++) {
               //If statement that checks if the spot selected is adjacent to 3 of the same value horizontally and will return true to end the game if condition met
                if (board[r][c] == player && board[r][c + 1] == player && board[r][c + 2] == player && board[r][c + 3] == player) {
                    return true;
                }
            }
        }
        //Second for loop that runs through each column, working from left to right
        for(int c = 0; c < board.length + 1; c++){
            //Second secondary for loop that will check each spot in said column by going thorugh each individually starting from bottom to top
            for(int r = board.length - 1; r != -1; r--){
                //If statement that checks if the spot selected is adjacent to 3 of the same value vertically and will return true to end the game if condition met
                if(board[r][c] == player && board[r - 1][c] == player && board[r - 2][c] == player && board[r - 3][c] == player){
                    return true;
                }
            }
        }
        //If both don't meet the 4 in a row/column then return false and let the game continue
        return false;
    }

    /**
     *  This method looks for four in a row diagonally right to left.
     * For example .---.---.---.---.
     *             |   |   |   | X |
     *             .---.---.---.---.
     *             |   |   | X |   |
     *             .---.---.---.---.
     *             |   | X |   |   |
     *             .---.---.---.---.
     *             | X |   |   |   |
     *             .---.---.---.---.
     * @param player represents the current player.  The value will either be RED (1) or BLACK (2).
     * @return true if four in a row can be found in either orientation, otherwise false.
     */
    private boolean checkDiagonalLeft(int player) {
        //For loop that will start from the bottom of the array and work upwards
        for(int r = board.length - 1; r != -1; r--){
           //Secondary for loop that will check each spot corresponding with the counting value in said row
            for(int c = 0; c < board.length - 2; c++){
               //If statement that checks if there are 4 in a row diagonally from bottom left to top right and returns true and ends the game if so
                if(board[r][c] == player && board[r - 1][c + 1] == player && board[r - 2][c + 2] == player && board[r - 3][c + 3] == player){
                    return true;
                }
            }
        }
        //If the for loop never returns true then the game will continue
        return false;
    }

    /**
     *  This method looks for four in a row diagonally left to right.
     * For example .---.---.---.---.
     *             | X |   |   |   |
     *             .---.---.---.---.
     *             |   | X |   |   |
     *             .---.---.---.---.
     *             |   |   | X |   |
     *             .---.---.---.---.
     *             |   |   |   | X |
     *             .---.---.---.---.
     * @param player represents the current player.  The value will either be RED (1) or BLACK (2).
     * @return true if four in a row can be found in either orientation, otherwise false.
     */
    private boolean checkDiagonalRight(int player) {
        //For loop that will start from the top of the array and work downwards
        for(int r = 0; r < board.length - 3; r++){
            //Secondary for loop that will check each spot corresponding with the counting value in said row
            for(int c = 0; c < board.length - 1; c++){
                //If statement that checks if there are 4 in a row diagonally from top left to bottom right and returns true and ends the game if so
                if(board[r][c] == player && board[r + 1][c + 1] == player && board[r + 2][c + 2] == player && board[r + 3][c + 3] == player){
                    return true;
                }
            }
        }
        //If the for loop never returns true then the game will continue
        return false;
    }

    /**
     * This method determines if the current player has won by checking all possible
     * outcomes on the board.
     * @param player represents the current player.  The value will either be RED (1) or BLACK (2).
     * @return the player number (matches @param) if four in a row can be found.  If the player
     *         did not win, return 0.
     */
    public int checkWinner(int player) {
        if(checkRows(player) || checkDiagonalRight(player) || checkDiagonalLeft(player)) {
            return player;
        } else {
            return 0;
        }
    }

    /* This method prints the board to the console.  Note that numbers correspond to human
     * intuition, where the 1st column is labeled "1", not "0" as would be expected for array's
     * index value.
     * YOU DO NOT NEED TO MODIFY THIS CODE
     */
    public void printBoard() {
        for(int r = 0; r < board.length; r++) {
            for(int i = 0; i < board[0].length; i++) System.out.print(".---");
            System.out.println(".");
            for(int c = 0; c < board[0].length; c++) {
                System.out.print("|");
                if(board[r][c] == Game.RED) System.out.print(" R ");
                else if(board[r][c] == Game.BLACK) System.out.print(" B ");
                else System.out.print("   ");
            }
            System.out.println("|");
        }
        for(int i = 0; i < board[0].length; i++) System.out.print(".---");
        System.out.println(".");
        for(int i = 0; i < board[0].length; i++) System.out.print("  " + (i+1) + " ");
        System.out.println("\n");
        //for(int i = 0; i < COLS; i++) System.out.print("  " + chipCount[i] + " ");
        //System.out.println("\n");
    }

    public int[][] getBoardCopy() {
        int[][] copy = new int[board.length][board[0].length];
        for(int r = 0; r < copy.length; r++) {
            for(int c = 0; c < copy[0].length; c++) {
                copy[r][c] = board[r][c];
            }
        }
        return copy;
    }

}
```
## To determine winner
```java
import java.util.Scanner;

public class Game {
    public static final int EMPTY = 0;
    public static final int RED = 1;  //The RED player is considerd Player 1
    public static final int BLACK = 2;  //The BLACK player is considered Player 2
    public static final int ROWS = 6;  //The number of rows for the game
    public static final int COLS = 7;  //The number of columns for the game

    /* This is the main method that controls the flow of the game.
     */
    public static void main(String[] args) {
        ConnectFour game = new ConnectFour();
        Scanner in = new Scanner(System.in);
        int turn = RED;
        int column = COLS;
        boolean quit = false;
        boolean gameEnd = false;

        Player redPlayer = new Player("Player 1", RED);
        Player blackPlayer = new Player("Player 2", BLACK);
        Player currentPlayer = redPlayer;
        game.printBoard();

        while(!gameEnd) {
            if(turn == RED) {
                System.out.println("RED Player: Select your Column 1 - " + COLS);
                currentPlayer = redPlayer;
            } else {
                System.out.println("BLACK Player: Select your Column 1 - " + COLS);
                currentPlayer = blackPlayer;
            }

            column = currentPlayer.chooseColumn(game.getBoardCopy());

            if(column < 0) {
                quit = true;
                break;
            }
            if(!game.isFull(column)) {
                game.placeChip(column, turn);
            }

            game.printBoard();
            if(game.checkWinner(turn) != 0)
                gameEnd = true;
            else if(turn == RED)
                turn = BLACK;
            else if(turn == BLACK)
                turn = RED;
        }
        if(quit)
            System.out.println("GAME ENDED. NO WINNER =(");
        else if(turn == RED)
            System.out.println("RED PLAYER WINS!");
        else
            System.out.println("BLACK PLAYER WINS!");
    }

}
```

## Changes player turn and allows them to choose which column
```java
import java.util.Scanner;

public class Player {
    private String name;
    private int myColor;

    public Player(String name, int player) {
        this.name = name;
        myColor = player;
    }

    public int chooseColumn(int[][] board) {
        Scanner scan = new Scanner(System.in);
        int choice = scan.nextInt();
        return choice;
    }
}
```
