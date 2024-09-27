..........code...........

#include <stdio.h>



#define rows 7   //defining of number of rows

#define columns 7   //defining of number of columns

#define first_player 'X'     

#define second_player 'O'



char board[rows][columns];   



// Function to display the current state of the board

void display_board() {

    printf("\n");

    int i,j;

    for (i = 0; i < rows; i++) {

        for (j = 0; j < columns; j++) {

            printf("| %c ", board[i][j]);

        }

        printf("|\n");

    }

    printf("  1   2   3   4   5   6   7\n");

}



// Function to check if a player has won

int check_winner(char player) {

    // Check for horizontal wins

    int i,j;

    for ( i = 0; i < rows; i++) {

        for (j = 0; j <= columns - 3; j++) {

            if (board[i][j] == player && board[i][j+1] == player && board[i][j+2] == player) {

                return 1;

            }

        }

    }

    // Check for vertical wins

    for (i = 0; i <= rows - 3; i++) {

        for ( j = 0; j < columns; j++) {

            if (board[i][j] == player && board[i+1][j] == player && board[i+2][j] == player) {

                return 1;

            }

        }

    }



    // Check for diagonal wins (top left to bottom right)

    for (i = 0; i <= rows - 3; i++) {

        for (j = 0; j <= columns - 3; j++) {

            if (board[i][j] == player && board[i+1][j+1] == player && board[i+2][j+2] == player) {

                return 1;

            }

        }

    }



    // Check for diagonal wins (bottom left to top right)

    for (i = rows - 1; i >= 2; i--) {

        for ( j = 0; j <= columns - 3; j++) {

            if (board[i][j] == player && board[i-1][j+1] == player && board[i-2][j+2] == player) {

                return 1;

            }

        }

    }



    // No winner yet

    return 0;

}



// Function to check if the game is a draw

int check_draw() {

    int i,j;

	for ( i = 0; i < rows; i++) {

        for ( j = 0; j < columns; j++) {

            if (board[i][j] == ' ') {

                return 0;

            }

        }

    }

    return 1;

}



// Function to get the column where the player wants to make a move

int get_column(char player) {

    int column;

    do {

        printf("Player %c, enter the column (1-7) where you want to make a move: ", player);

        scanf("%d", &column);

    } while (column < 1 || column > 7 || board[0][column-1] != ' ');

    return column-1;

}



int main() {

    int turn_count = 0;

    char current_player = first_player;



    // Initialize the board to all empty spaces

   int i,j;

   for (i = 0; i < rows; i++) {

    for ( j = 0; j < columns; j++) {

        board[i][j] = ' ';

    }

}



// Main game loop

do {

    display_board();

    int column = get_column(current_player);



    // Make the move

    int row;

    for (row = rows-1; row >= 0; row--) {

        if (board[row][column] == ' ') {

            board[row][column] = current_player;

            break;

        }

    }



    // Check for a winner

    if (check_winner(current_player)) {

        display_board();

        printf("Player %c wins!\n", current_player);

        break;

    }



    // Check for a draw

    if (check_draw()) {

        display_board();

        printf("The game is a draw.\n");

        break;

    }



    // Switch to the other player's turn

    if (current_player == first_player) {

        current_player = second_player;

    } else {

        current_player = first_player;

    }

    turn_count++;

} while (1);



return 0;

}





