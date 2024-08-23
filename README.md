import java.util.Scanner;//I used this such as to take input 
import java.util.Random;// I used this such as the system will generate any random number for the user to guess 
public class Javaproject1 {
    public static void main(String[] args) {
        Scanner scanner=new Scanner(System.in); Random random=new Random();
        int count=0;//I used this to count the number of attempts
        int startingpoint=1;
        int endingpoint=100;
        int randomNumber = random.nextInt(endingpoint - startingpoint + 1) + startingpoint;//I used this such as the system chooses any number between the bound
        int maximumattempt = 15;
        boolean userhasWon = false;

        System.out.println("HURRAY! Welcome to Guess the Number!");
        System.out.println("I have randomly selected a number between " + startingpoint + " and " + endingpoint + ".");
        System.out.println("Can you guess what the number is? You have " + maximumattempt + " attempts so choose wisely");

        while (count < maximumattempt) {
            System.out.print("Enter your guess: ");
            int Guess = scanner.nextInt();
            count++;

            if (Guess < startingpoint || Guess > endingpoint) {
                System.out.println("Please enter your number between " + startingpoint + " and " + endingpoint + ".");
            } else if (Guess > randomNumber) {
                System.out.println("It is very HIGH!!! Try again");
            } else if (Guess < randomNumber) {
                System.out.println("It is very LOW!!! Try again");
            } else {
                System.out.println("BRAVO!! You guessed the number in " + count + " attempts.");
                userhasWon = true;
                break;
            }
        }
       if (userhasWon==false) {
            System.out.println("Apologies from my side . The correct number was" + randomNumber + ".");
        }

        scanner.close();
    }
}

