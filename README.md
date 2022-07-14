# TicTacToe
Java - Tic-Tac-Toe Game

DESIGNING A TIC TAC TOE GAME IN JAVA
Here is the board template:

   |   |  
---+---+---
   |   |  
---+---+---
   |   |
The board was designed using the print statement in Java i.e System.out.println();
While the space to be filled with String varaibles of either 'X' or 'O' is represented in an Array of Characters i.e char[] pos
Interger input is taken from players with change of turns and fixing the turns in the inputed positions



import java.util.Scanner;

public class TicTacToe {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int input;
        // Char has single quote
        char[] pos = {' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '};
        // Setting turn
        char turn = 'X';
        // To keep count of turns set to 1
        int currentTurn = 1;
        // While loops continues
        while(true) {
            // to avoid overlapping of turns
            do {
                System.out.println(turn+ " Enter a position: ");
                input = scan.nextInt();
            }while (pos[input-1]=='X' || pos[input-1]=='O');
            // Subtract 1 from user input to match array index
            //Setting the value to turn
            pos[input - 1] = turn;

            System.out.println(" " + pos[6] + " | " + pos[7] + " | " + pos[8] + " ");
            System.out.println("---+---+---");
            System.out.println(" " + pos[3] + " | " + pos[4] + " | " + pos[5] + " ");
            System.out.println("---+---+---");
            System.out.println(" " + pos[0] + " | " + pos[1] + " | " + pos[2] + " ");
            //Enter possible combinations to win
            if ((pos[0] == turn && pos[1] == turn && pos[2] == turn) ||
                (pos[3] == turn && pos[4] == turn && pos[5] == turn) ||
                (pos[6] == turn && pos[7] == turn && pos[8] == turn) ||
                (pos[0] == turn && pos[4] == turn && pos[8] == turn) ||
                (pos[0] == turn && pos[3] == turn && pos[6] == turn) ||
                (pos[1] == turn && pos[4] == turn && pos[7] == turn) ||
                (pos[2] == turn && pos[5] == turn && pos[8] == turn) ||
                (pos[2] == turn && pos[4] == turn && pos[6] == turn)){
                System.out.println(turn + " is the WINNER");
                //Break out of the loop to end the game
                break;
            }
            // Taking turn between 'X' and 'O' --> alternating
            if (turn == 'X'){
                turn = 'O';
            } else if (turn == 'O') {
                turn = 'X';

            }
            currentTurn++;
            //Checking if all spaced have been filled without a winner
            if(currentTurn > 9){
                System.out.println("DRAW");
        }

        }
    }
}
