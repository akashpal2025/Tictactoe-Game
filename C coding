#include <stdio.h>

char board[3][3];


void initializeBoard() {
    char ch = '1';
    for(int i = 0; i < 3; i++) {
        for(int j = 0; j < 3; j++) {
            board[i][j] = ch++;
        }
    }
}


void displayBoard() {
    printf("\n");
    for(int i = 0; i < 3; i++) {
        printf(" %c | %c | %c ", board[i][0], board[i][1], board[i][2]);
        if(i < 2)
            printf("\n---|---|---\n");
    }
    printf("\n\n");
}


int checkWin() {
    
    for(int i = 0; i < 3; i++) {
        if(board[i][0] == board[i][1] && board[i][1] == board[i][2])
            return 1;
        if(board[0][i] == board[1][i] && board[1][i] == board[2][i])
            return 1;
    }


    if(board[0][0] == board[1][1] && board[1][1] == board[2][2])
        return 1;
    if(board[0][2] == board[1][1] && board[1][1] == board[2][0])
        return 1;

    return 0;
}


int checkDraw() {
    for(int i = 0; i < 3; i++) {
        for(int j = 0; j < 3; j++) {
            if(board[i][j] != 'X' && board[i][j] != 'O')
                return 0;
        }
    }
    return 1;
}


int main() {
    int choice, row, col;
    char player = 'X';

    initializeBoard();

    while(1) {
        displayBoard();

        printf("Player %c, enter your choice (1-9): ", player);
        scanf("%d", &choice);

        row = (choice - 1) / 3;
        col = (choice - 1) % 3;

        
        if(board[row][col] == 'X' || board[row][col] == 'O') {
            printf("Invalid move! Try again.\n");
            continue;
        }

        board[row][col] = player;

        
        if(checkWin()) {
            displayBoard();
            printf("🎉 Player %c wins!\n", player);
            break;
        }

        
        if(checkDraw()) {
            displayBoard();
            printf("It's a draw!\n");
            break;
        }

        
        player = (player == 'X') ? 'O' : 'X';
    }

    return 0;
}
