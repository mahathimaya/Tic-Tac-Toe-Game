import java.util.Scanner;

public class TicTacToe {
    private char[][] board = new char[3][3]; // Game board
    private char currentPlayer = 'X'; // Starting player

    public TicTacToe() {
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                board[i][j] = '-'; // Initialize empty board
            }
        }
    }

    public void printBoard() {
        for (char[] row : board) {
            System.out.println(row);
        }
    }

    public boolean isBoardFull() {
        for (char[] row : board) {
            for (char cell : row) {
                if (cell == '-') return false; // Found an empty cell
            }
        }
        return true; // No empty cells
    }

    public boolean checkForWin() {
        return checkRows() || checkColumns() || checkDiagonals();
    }

    private boolean checkRows() {
        for (char[] row : board) {
            if (row[0] == currentPlayer && row[1] == currentPlayer && row[2] == currentPlayer) {
                return true; // Winning row
            }
        }
        return false;
    }

    private boolean checkColumns() {
        for (int i = 0; i < 3; i++) {
            if (board[0][i] == currentPlayer && board[1][i] == currentPlayer && board[2][i] == currentPlayer) {
                return true; // Winning column
            }
        }
        return false;
    }

    private boolean checkDiagonals() {
        return (board[0][0] == currentPlayer && board[1][1] == currentPlayer && board[2][2] == currentPlayer) ||
                (board[0][2] == currentPlayer && board[1][1] == currentPlayer && board[2][0] == currentPlayer);
    }

    public void changePlayer() {
        currentPlayer = (currentPlayer == 'X') ? 'O' : 'X'; // Switch player
    }

    public void playGame() {
        Scanner scanner = new Scanner(System.in);
        while (true) {
            printBoard();
            System.out.println("Current player: " + currentPlayer);
            System.out.print("Enter row and column (0-2): ");
            int row = scanner.nextInt();
            int col = scanner.nextInt();

            if (row >= 0 && row < 3 && col >= 0 && col < 3 && board[row][col] == '-') {
                board[row][col] = currentPlayer; // Place move

                if (checkForWin()) {
                    printBoard();
                    System.out.println("Player " + currentPlayer + " wins!");
                    break;
                }
                if (isBoardFull()) {
                    printBoard();
                    System.out.println("The game is a draw!");
                    break;
                }
                changePlayer(); // Switch to next player
            } else {
                System.out.println("Invalid move. Try again.");
            }
        }
        scanner.close();
    }

    public static void main(String[] args) {
        new TicTacToe().playGame(); // Start the game
    }
}
