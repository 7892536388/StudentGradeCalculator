# StudentGradeCalculator
import java.util.Scanner;

public class StudentGradeCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        
       System.out.print("Enter the number of subjects: ");
        int numSubjects = scanner.nextInt();
        double[] marks = new double[numSubjects];

        // Input marks for each subject
        for (int i = 0; i < numSubjects; i++) {
            System.out.print("Enter marks for subject " + (i + 1) + " (out of 100): ");
            marks[i] = scanner.nextDouble();
        }

        // Calculate total and average
        double totalMarks = 0;
        for (double mark : marks) {
            totalMarks += mark;
        }
        double averagePercentage = totalMarks / numSubjects;

        // Determine grade based on average percentage
        String grade;
        if (averagePercentage >= 90) {
            grade = "A";
        } else if (averagePercentage >= 80) {
            grade = "B";
        } else if (averagePercentage >= 70) {
            grade = "C";
        } else if (averagePercentage >= 60) {
            grade = "D";
        } else {
            grade = "F";
        }

        // Display results
        System.out.println("\nResults:");
        System.out.println("Total Marks: " + totalMarks + " out of " + (numSubjects * 100));
        System.out.println("Average Percentage: " + String.format("%.2f", averagePercentage) + "%");
        System.out.println("Grade: " + grade);

        scanner.close();
    }
}
