# CODEALPHA
import java.util.ArrayList;
import java.util.Scanner;

public class StudentGrades {
    public static void main(String[] args) {
        ArrayList<Integer> grades = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("Enter student grades (type 'done' to finish):");

        while (scanner.hasNextInt()) {
            grades.add(scanner.nextInt());
        }

        if (grades.isEmpty()) {
            System.out.println("No grades were entered.");
        } else {
            int highest = findHighest(grades);
            int lowest = findLowest(grades);
            double average = calculateAverage(grades);

            System.out.println("Highest grade: " + highest);
            System.out.println("Lowest grade: " + lowest);
            System.out.println("Average grade: " + average);
        }

        scanner.close();
    }

    private static int findHighest(ArrayList<Integer> grades) {
        int highest = grades.get(0);
        for (int grade : grades) {
            if (grade > highest) {
                highest = grade;
            }
        }
        return highest;
    }

    private static int findLowest(ArrayList<Integer> grades) {
        int lowest = grades.get(0);
        for (int grade : grades) {
            if (grade < lowest) {
                lowest = grade;
            }
        }
        return lowest;
    }

    private static double calculateAverage(ArrayList<Integer> grades) {
        int sum = 0;
        for (int grade : grades) {
            sum += grade;
        }
        return sum / (double) grades.size();
    }
}
