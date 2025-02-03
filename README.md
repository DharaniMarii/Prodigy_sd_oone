package com.example;

import java.util.Random;
import java.util.Scanner;

public class GuessingGame {
    public static void main(String[] args) {
        // Create a Random object to generate random numbers
        Random random = new Random();
        int randomNumber = random.nextInt(100) + 1; // Random number between 1 and 100

        // Create a Scanner object to read user input
        Scanner scanner = new Scanner(System.in);

        int guess = 0;
        int numberOfTries = 0;

        // Game loop
        while (guess != randomNumber) {
            System.out.print("Enter your guess (1-100): ");
            guess = scanner.nextInt();
            numberOfTries++;

            if (guess < randomNumber) {
                System.out.println("Too low! Try again.");
            } else if (guess > randomNumber) {
                System.out.println("Too high! Try again.");
            } else {
                System.out.println("Congratulations! You guessed the number in " + numberOfTries + " tries.");
            }
        }

        // Close the scanner
        scanner.close();
    }
}
