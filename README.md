import java.util.Random;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        int numberToGuess = random.nextInt(100) + 1;
        int numberOfTries = 0;
        int guess;
        boolean win = false;

        System.out.println("Bem-vindo ao jogo de adivinhação de números!");
        System.out.println("Estou pensando em um número entre 1 e 100. Tente adivinhar!");

        while (!win) {
            System.out.print("Digite seu palpite: ");
            guess = scanner.nextInt();
            numberOfTries++;

            if (guess < 1 || guess > 100) {
                System.out.println("Por favor, digite um número entre 1 e 100.");
            } else if (guess < numberToGuess) {
                System.out.println("Muito baixo! Tente novamente.");
            } else if (guess > numberToGuess) {
                System.out.println("Muito alto! Tente novamente.");
            } else {
                win = true;
                System.out.println("Parabéns! Você adivinhou o número em " + numberOfTries + " tentativas.");
            }
        }

        scanner.close();
    }
}

