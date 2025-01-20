# Brainwave_Matrix_Intern
import java.util.Scanner;
class UserAccount {
    private double balance;
    private int pin;

    public UserAccount(double initialBalance, int pin) {
        this.balance = initialBalance;
        this.pin = pin;
    }
    public double getBalance() {
        return balance;
    }
    public boolean withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            return true;
        } else {
            return false; 
        }
    }
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    public boolean verifyPin(int inputPin) {
        return this.pin == inputPin;
    }

    public void changePin(int newPin) {
        this.pin = newPin;
    }
}

class ATM {
    private UserAccount account;
    private Scanner scanner;

    public ATM(UserAccount account) {
        this.account = account;
        this.scanner = new Scanner(System.in);
    }

    public void start() {
        System.out.println("Welcome to the ATM!");
        if (authenticate()) {
            boolean quit = false;
            while (!quit) {
                System.out.println("\nATM Menu:");
                System.out.println("1: Check Balance");
                System.out.println("2: Withdraw");
                System.out.println("3: Deposit");
                System.out.println("4: Change PIN");
                System.out.println("5: Exit");

                System.out.print("Choose an option: ");
                int choice = scanner.nextInt();

                switch (choice) {
                    case 1:
                        checkBalance();
                        break;
                    case 2:
                        withdraw();
                        break;
                    case 3:
                        deposit();
                        break;
                    case 4:
                        changePin();
                        break;
                    case 5:
                        quit = true;
                        System.out.println("Thank you for using the ATM. Goodbye!");
                        break;
                    default:
                        System.out.println("Invalid option. Please try again.");
                }
            }
        } else {
            System.out.println("Authentication failed. Exiting.");
        }
    }

    private boolean authenticate() {
        System.out.print("Enter your PIN: ");
        int inputPin = scanner.nextInt();
        return account.verifyPin(inputPin);
    }
    private void checkBalance() {
        System.out.println("Your balance is: $" + account.getBalance());
    }
    private void withdraw() {
        System.out.print("Enter the amount to withdraw: ");
        double amount = scanner.nextDouble();
        if (account.withdraw(amount)) {
            System.out.println("Withdrawal successful. New balance: $" + account.getBalance());
        } else {
            System.out.println("Insufficient funds or invalid amount.");
        }
    }
    private void deposit() {
        System.out.print("Enter the amount to deposit: ");
        double amount = scanner.nextDouble();
        account.deposit(amount);
        System.out.println("Deposit successful. New balance: $" + account.getBalance());
    }
    private void changePin() {
        System.out.print("Enter your new PIN: ");
        int newPin = scanner.nextInt();
        account.changePin(newPin);
        System.out.println("PIN changed successfully.");
    }
}

public class TASK1 {
    public static void main(String[] args) {
        UserAccount userAccount = new UserAccount(0.0, 1234);
        ATM atm = new ATM(userAccount);
        atm.start();
    }
}
# Brainwave_Matrix_Intern
import java.util.Scanner;
class UserAccount {
    private double balance;
    private int pin;

    public UserAccount(double initialBalance, int pin) {
        this.balance = initialBalance;
        this.pin = pin;
    }
    public double getBalance() {
        return balance;
    }
    public boolean withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            return true;
        } else {
            return false; 
        }
    }
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    public boolean verifyPin(int inputPin) {
        return this.pin == inputPin;
    }

    public void changePin(int newPin) {
        this.pin = newPin;
    }
}

class ATM {
    private UserAccount account;
    private Scanner scanner;

    public ATM(UserAccount account) {
        this.account = account;
        this.scanner = new Scanner(System.in);
    }

    public void start() {
        System.out.println("Welcome to the ATM!");
        if (authenticate()) {
            boolean quit = false;
            while (!quit) {
                System.out.println("\nATM Menu:");
                System.out.println("1: Check Balance");
                System.out.println("2: Withdraw");
                System.out.println("3: Deposit");
                System.out.println("4: Change PIN");
                System.out.println("5: Exit");

                System.out.print("Choose an option: ");
                int choice = scanner.nextInt();

                switch (choice) {
                    case 1:
                        checkBalance();
                        break;
                    case 2:
                        withdraw();
                        break;
                    case 3:
                        deposit();
                        break;
                    case 4:
                        changePin();
                        break;
                    case 5:
                        quit = true;
                        System.out.println("Thank you for using the ATM. Goodbye!");
                        break;
                    default:
                        System.out.println("Invalid option. Please try again.");
                }
            }
        } else {
            System.out.println("Authentication failed. Exiting.");
        }
    }

    private boolean authenticate() {
        System.out.print("Enter your PIN: ");
        int inputPin = scanner.nextInt();
        return account.verifyPin(inputPin);
    }
    private void checkBalance() {
        System.out.println("Your balance is: $" + account.getBalance());
    }
    private void withdraw() {
        System.out.print("Enter the amount to withdraw: ");
        double amount = scanner.nextDouble();
        if (account.withdraw(amount)) {
            System.out.println("Withdrawal successful. New balance: $" + account.getBalance());
        } else {
            System.out.println("Insufficient funds or invalid amount.");
        }
    }
    private void deposit() {
        System.out.print("Enter the amount to deposit: ");
        double amount = scanner.nextDouble();
        account.deposit(amount);
        System.out.println("Deposit successful. New balance: $" + account.getBalance());
    }
    private void changePin() {
        System.out.print("Enter your new PIN: ");
        int newPin = scanner.nextInt();
        account.changePin(newPin);
        System.out.println("PIN changed successfully.");
    }
}

public class TASK1 {
    public static void main(String[] args) {
        UserAccount userAccount = new UserAccount(0.0, 1234);
        ATM atm = new ATM(userAccount);
        atm.start();
    }
}
