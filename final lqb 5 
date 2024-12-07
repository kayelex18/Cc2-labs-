package cc2projects;
import javax.swing.JOptionPane; // Import JOptionPane for user input and output

//Custom Exception for Insufficient Funds
class InsufficientFundsException extends Exception {
 public InsufficientFundsException(String message) {
     super(message); // Call the parent class constructor with the error message
 }
}

//Banking System Class
class BankAccount {
 private double balance; // Variable to store the account balance

 // Constructor to initialize the bank account with an initial balance
 public BankAccount(double initialBalance) {
     this.balance = initialBalance;
 }

 // Method to withdraw money from the account
 public void withdraw(double amount) throws InsufficientFundsException {
     // Check if the withdrawal amount exceeds the current balance
     if (amount > balance) {
         throw new InsufficientFundsException("Withdrawal amount exceeds the current balance.");
     }
     // Deduct the amount from the balance
     balance -= amount;
     // Show the new balance after withdrawal
     JOptionPane.showMessageDialog(null, String.format("Successfully withdrew %.2f. New balance: %.2f", amount, balance));
 }

 // Method to get the current balance
 public double getBalance() {
     return balance;
 }
}

//Main Class
public class ExceptionHandling {
 public static void main(String[] args) {
     // Get the initial balance from the user
     String initialBalanceStr = JOptionPane.showInputDialog("Enter initial balance: ");
     double initialBalance = Double.parseDouble(initialBalanceStr); // Convert input to double
     BankAccount account = new BankAccount(initialBalance); // Create a bank account with the initial balance

     // Get the withdrawal amount from the user
     String amountToWithdrawStr = JOptionPane.showInputDialog("Enter amount to withdraw: ");
     double amountToWithdraw = Double.parseDouble(amountToWithdrawStr); // Convert input to double

     try {
         account.withdraw(amountToWithdraw); // Try to withdraw the specified amount
     } catch (InsufficientFundsException e) {
         // Catch and display the error message if withdrawal fails
         JOptionPane.showMessageDialog(null, "Error: " + e.getMessage());
     }

     // Display the current balance
     JOptionPane.showMessageDialog(null, String.format("Current balance: %.2f", account.getBalance()));
 }
}