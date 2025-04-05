# Ap-assignment-3rd

#Implement a custom exception InvalidAgeException that is thrown when a user enters an age below 18 while creating an account.

class InvalidAgeException extends Exception {
    public InvalidAgeException(String message) {
        super(message);
    }
}
class UserAccount {
    private String name;
    private int age;

    public UserAccount(String name, int age) throws InvalidAgeException {
        if (age < 18) {
            throw new InvalidAgeException("Age must be 18 or above to create an account.");
        }
        this.name = name;
        this.age = age;
        System.out.println("Account created successfully for " + name);
    }
}
public class Main {
    public static void main(String[] args) {
        try {
            UserAccount user1 = new UserAccount("Anshuman", 20);
            UserAccount user2 = new UserAccount("Himanshu", 16); // 
        } catch (InvalidAgeException e) {
            System.out.println("Exception: " + e.getMessage());
        }
    }
}

