import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

class User {
    private String username;
    private String password;

    public User(String username, String password) {
        this.username = username;
        this.password = password;
    }

    // Getters and setters for username and password
}

class Expense {
    private String date;
    private String category;
    private double amount;

    public Expense(String date, String category, double amount) {
        this.date = date;
        this.category = category;
        this.amount = amount;
    }

    // Getters and setters for date, category, and amount
}

class ExpenseManager {
    private List<User> users;
    private List<Expense> expenses;

    public ExpenseManager() {
        this.users = new ArrayList<>();
        this.expenses = new ArrayList<>();
    }

    public void registerUser(String username, String password) {
        User newUser = new User(username, password);
        users.add(newUser);
        System.out.println("User registered successfully!");
    }

    public void addExpense(String date, String category, double amount) {
        Expense newExpense = new Expense(date, category, amount);
        expenses.add(newExpense);
        System.out.println("Expense added successfully!");
    }

    // Additional methods for listing expenses, calculating category-wise summation, and persistence can be added here.
}

public class Main {
    public static void main(String[] args) {
        ExpenseManager expenseManager = new ExpenseManager();
        Scanner scanner = new Scanner(System.in);

        // User Registration
        System.out.print("Enter username: ");
        String username = scanner.nextLine();
        System.out.print("Enter password: ");
        String password = scanner.nextLine();
        expenseManager.registerUser(username, password);

        // Expense Entry
        System.out.print("Enter expense date: ");
        String date = scanner.nextLine();
        System.out.print("Enter expense category: ");
        String category = scanner.nextLine();
        System.out.print("Enter expense amount: ");
        double amount = scanner.nextDouble();
        expenseManager.addExpense(date, category, amount);

        // Additional functionalities can be added here.
    }
}
