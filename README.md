# Student-Academic-Decision-System                                                                                                                                
import java.util.Scanner;

public class StudentAcademicSystem {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in); 

        // Student information variables
        String student_name; 
        int age;
        int mark;
        int attendance; 
        boolean student_category = false;
        String academicResult = "";

        // Inputs
        System.out.print("Enter your name: ");
        student_name = input.nextLine();

        System.out.print("Enter your age: ");
        age = input.nextInt();

        System.out.print("Enter your mark: ");
        mark = input.nextInt();

        System.out.print("Enter your Attendance: ");
        attendance = input.nextInt();
        
        // Display student information
        System.out.println("\n  Student Information ");
        System.out.println("Name: " + student_name);
        System.out.println("Age: " + age);
        System.out.println("Mark: " + mark + "%");
        System.out.println("Attendance: " + attendance + "%");

        // Age decision
        if (age >= 18) {
            System.out.println("Status: Adult");
        } else {
            System.out.println("Status: Minor");
        }

        // Special category setup
        if (age < 18 || age > 60) {
            student_category = true;
            System.out.println("Category: Special Category");
        } else {
            student_category = false;
            System.out.println("Category: Regular Category");
        }

        // Updated grade distribution using if-else-if
        if (mark >= 0 && mark <= 100) {
            if (mark >= 90) {
                academicResult = "Excellent";
            } else if (mark >= 75) {
                academicResult = "Very Good";
            } else if (mark >= 60) {
                academicResult = "Good";
            } else if (mark >= 50) {
                academicResult = "Pass";
            } else {
                academicResult = "Fail";
            }
            System.out.println("Academic Result: " + academicResult);
        } else {
            System.out.println("Invalid Mark! Must be between 0 and 100.");
            academicResult = "Invalid";
        }

        // Exam eligibility
        if (mark >= 50 && attendance >= 75) {
            System.out.println("Exam Eligibility: Qualified");
        } else {
            System.out.println("Exam Eligibility: Did not qualify");
        }

        // Admission condition check
        if (age >= 18 && mark >= 50 && attendance >= 75) {
            System.out.println("Admission Status: Admitted");
        } else {
            System.out.println("Admission Status: Not Admitted");
        }

        // academic support check
        if (mark < 40 || attendance < 50) {
            System.out.println("Support Status: Academic support required.");
        }

        //Fee discount decision
        double discount;
        if (student_category) {
            discount = 0.20; // 20% discount
        } else {
            discount = 0.05; // 5% discount
        }

        // Service menu using switch
        System.out.println("\n Service Menu ");
        System.out.println("1: Academic Results");
        System.out.println("2: Attendance");
        System.out.println("3: Fees");
        System.out.println("4: Student Support");
        System.out.println("5: Exit");
        System.out.print("Select an option: ");
        int user_input = input.nextInt();
        
        switch (user_input) {
            case 1:
                System.out.println("Results: " + academicResult);
                break;
            case 2:
                System.out.println("Attendance Record: " + attendance + "%");
                break;
            case 3:
                System.out.println("Fees: Your eligible discount is " + (int)(discount * 100) + "%");
                break;
            case 4:
                System.out.println("Student Support: Contact drsqueries@rosebankcollege.co.za");
                break;
            case 5:
                System.out.println("Exiting system");
                break;
            default:
                System.out.println("Invalid menu option selected.");
                break;
        }
        
        
    }
}
