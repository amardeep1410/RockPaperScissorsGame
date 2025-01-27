# RockPaperScissorsGame
import java.util.Random;
import java.util.Scanner;

public class RockPaperScissorsGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        
        System.out.println("Welcome to Rock, Paper, Scissors!");
        System.out.println("Choose your move:");
        System.out.println("1. Rock");
        System.out.println("2. Paper");
        System.out.println("3. Scissors");

        System.out.print("Enter your choice (1/2/3): ");
        int userChoice = scanner.nextInt();

        Random random = new Random();
        int computerChoice = random.nextInt(3) + 1;  // Random number between 1 and 3

        System.out.println("Your choice: " + getChoiceName(userChoice));
        System.out.println("Computer's choice: " + getChoiceName(computerChoice));

        String result = determineWinner(userChoice, computerChoice);
        System.out.println(result);

        scanner.close();
    }

    public static String getChoiceName(int choice) {
        switch (choice) {
            case 1: return "Rock";
            case 2: return "Paper";
            case 3: return "Scissors";
            default: return "Invalid";
        }
    }

    public static String determineWinner(int userChoice, int computerChoice) {
        if (userChoice == computerChoice) {
            return "It's a tie!";
        } else if ((userChoice == 1 && computerChoice == 3) || 
                   (userChoice == 2 && computerChoice == 1) || 
                   (userChoice == 3 && computerChoice == 2)) {
            return "You win!";
        } else {
            return "Computer wins!";
        }
    }
}
