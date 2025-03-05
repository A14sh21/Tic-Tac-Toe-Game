import java.util.Scanner;

class Main {
  public static void main(String[] args) {
    char[][] board = new char[3][3];
    initializeBoard(board);
    
    char player = 'X';
    boolean gameOver = false;
    Scanner scanner = new Scanner(System.in);

    while (!gameOver) {
      printBoard(board);
      System.out.print("Player " + player + " enter row and column: ");
      int row = scanner.nextInt();
      int col = scanner.nextInt();
      
      if (isValidMove(board, row, col)) {
        board[row][col] = player;
        gameOver = checkWin(board, player);
        if (gameOver) {
          printBoard(board);
          System.out.println("Player " + player + " has won!");
        } else {
          player = (player == 'X') ? 'O' : 'X';
        }
      } else {
        System.out.println("Invalid move. Try again!");
      }
    }
    scanner.close();
  }

  private static void initializeBoard(char[][] board) {
    for (int row = 0; row < 3; row++) {
      for (int col = 0; col < 3; col++) {
        board[row][col] = ' ';
      }
    }
  }

  private static boolean isValidMove(char[][] board, int row, int col) {
    return row >= 0 && row < 3 && col >= 0 && col < 3 && board[row][col] == ' ';
  }

  private static boolean checkWin(char[][] board, char player) {
    for (int i = 0; i < 3; i++) {
      if ((board[i][0] == player && board[i][1] == player && board[i][2] == player) || 
          (board[0][i] == player && board[1][i] == player && board[2][i] == player)) {
        return true;
      }
    }
    return (board[0][0] == player && board[1][1] == player && board[2][2] == player) || 
           (board[0][2] == player && board[1][1] == player && board[2][0] == player);
  }

  private static void printBoard(char[][] board) {
    for (int row = 0; row < 3; row++) {
      System.out.println("  " + board[row][0] + " | " + board[row][1] + " | " + board[row][2]);
      if (row < 2) {
        System.out.println(" ---+---+---");
      }
    }
    System.out.println();
  }
}
