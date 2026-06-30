# Student Grade Tracker

## Java Source Code

``` java
import java.util.ArrayList;
import java.util.Scanner;

public class StudentGradeTracker {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        ArrayList<String> studentNames = new ArrayList<>();
        ArrayList<Double> studentGrades = new ArrayList<>();

        System.out.print("Enter the number of students: ");
        int n = sc.nextInt();
        sc.nextLine();

        for (int i = 0; i < n; i++) {
            System.out.println("\nStudent " + (i + 1));
            System.out.print("Enter Name: ");
            String name = sc.nextLine();

            System.out.print("Enter Grade: ");
            double grade = sc.nextDouble();
            sc.nextLine();

            studentNames.add(name);
            studentGrades.add(grade);
        }

        double total = 0;
        double highest = studentGrades.get(0);
        double lowest = studentGrades.get(0);

        for (double grade : studentGrades) {
            total += grade;
            if (grade > highest) highest = grade;
            if (grade < lowest) lowest = grade;
        }

        double average = total / n;

        System.out.println("\n========== STUDENT GRADE REPORT ==========");
        System.out.printf("%-20s %-10s\n", "Student Name", "Grade");
        System.out.println("-----------------------------------------");

        for (int i = 0; i < n; i++) {
            System.out.printf("%-20s %-10.2f\n",
                    studentNames.get(i),
                    studentGrades.get(i));
        }

        System.out.println("-----------------------------------------");
        System.out.printf("Average Grade : %.2f\n", average);
        System.out.printf("Highest Grade : %.2f\n", highest);
        System.out.printf("Lowest Grade  : %.2f\n", lowest);

        sc.close();
    }
}
```
