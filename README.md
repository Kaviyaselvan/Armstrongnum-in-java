# Armstrongnum-in-java
import java.util.Scanner;

public class ArmstrongNum {
    public static String isAmst(int num) {
        int n = num, temp, totalDigit = 0, original = n;
        while (n > 0) {
            n = n / 10;
            totalDigit++;
        }
        n = original;
        int armstrong = 0;
        while (n > 0) {
            temp = n % 10;
            armstrong += (int) Math.pow(temp, totalDigit);
            n = n / 10;
        }
        if (armstrong == original) {
            return "yes";
        } else {
            return "no";
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a number: ");

        if (scanner.hasNextInt()) {
            int n = scanner.nextInt();
            System.out.println(isAmst(n));
        }

        scanner.close();
    }
}
