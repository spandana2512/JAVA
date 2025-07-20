import java.util.Scanner;

public class ExaminationSystem {

    static String username = "student";
    static String password = "1234";
    static Scanner sc = new Scanner(System.in);

    public static void main(String[] args) {
        if (login()) {
            System.out.println("\nLogin Successful!");
            startExam();
        } else {
            System.out.println("\nLogin Failed. Exiting...");
        }
    }

    static boolean login() {
        System.out.println("====== LOGIN ======");
        System.out.print("Enter Username: ");
        String user = sc.nextLine();

        System.out.print("Enter Password: ");
        String pass = sc.nextLine();

        return user.equals(username) && pass.equals(password);
    }

    static void startExam() {
        int score = 0;

        System.out.println("\n====== ECE MCQ TEST ======\n");

        System.out.println("Q1. What is the unit of capacitance?");
        System.out.println("A. Ohm\nB. Farad\nC. Henry\nD. Watt");
        System.out.print("Answer: ");
        String ans1 = sc.nextLine();
        if (ans1.equalsIgnoreCase("B")) score++;

        System.out.println("\nQ2. Which logic gate gives a HIGH output only when all inputs are HIGH?");
        System.out.println("A. OR\nB. AND\nC. NAND\nD. NOR");
        System.out.print("Answer: ");
        String ans2 = sc.nextLine();
        if (ans2.equalsIgnoreCase("B")) score++;

        System.out.println("\nQ3. What is the bandwidth of a signal?");
        System.out.println("A. The signal strength\nB. The frequency difference\nC. Signal phase\nD. Signal wavelength");
        System.out.print("Answer: ");
        String ans3 = sc.nextLine();
        if (ans3.equalsIgnoreCase("B")) score++;

        System.out.println("\nQ4. Which device is used to convert analog signals to digital?");
        System.out.println("A. DAC\nB. Modulator\nC. ADC\nD. Transistor");
        System.out.print("Answer: ");
        String ans4 = sc.nextLine();
        if (ans4.equalsIgnoreCase("C")) score++;

        System.out.println("\nQ5. What does a diode do?");
        System.out.println("A. Amplifies current\nB. Stores charge\nC. Blocks DC\nD. Allows current in one direction");
        System.out.print("Answer: ");
        String ans5 = sc.nextLine();
        if (ans5.equalsIgnoreCase("D")) score++;

        showResult(score);
    }

    static void showResult(int score) {
        System.out.println("\n====== RESULT ======");
        System.out.println("Total Questions: 5");
        System.out.println("Correct Answers: " + score);
        System.out.println("Wrong Answers: " + (5 - score));
        System.out.println("Your Score: " + (score * 20) + "%");

        if (score >= 3) {
            System.out.println("Result: PASS");
        } else {
            System.out.println("Result: FAIL");
        }

        System.out.println("Thank you for taking the exam!");
    }
}
