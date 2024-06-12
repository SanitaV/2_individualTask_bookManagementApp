# TASK: Develop a simple book management application with ArrayList.
## *User should be able to add a book to ArrayList.*
## *User should be able to remove a book from ArrayList.*

### *Easy: Work with String in ArrayList. All the actions should be available for user.*
### *Medium: Work with String User should be able to repeat all the actions infinitely.*
```java
import java.util.ArrayList;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        BookManagementProgram bookManagementProgram = new BookManagementProgram();
        Scanner scanner = new Scanner(System.in);
        boolean exit = false;

        while (!exit) {
            System.out.println("\nBook Management Application:");
            System.out.println("1. Add a book");
            System.out.println("2. Remove a book");
            System.out.println("3. View all books");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");
            int choice = scanner.nextInt();
            scanner.nextLine(); 

            if (choice == 1) {
                System.out.print("Enter the name of the book to add: ");
                String bookToAdd = scanner.nextLine();
                bookManagementProgram.addBook(bookToAdd);
            } else if (choice == 2) {
                System.out.print("Enter the name of the book to remove: ");
                String bookToRemove = scanner.nextLine();
                bookManagementProgram.removeBook(bookToRemove);
            } else if (choice == 3) {
                bookManagementProgram.viewBooks();
            } else if (choice == 4) {
                exit = true;
                System.out.println("Exiting the application.");
            } else {
                System.out.println("Invalid choice. Please try again.");
            }
        }

        scanner.close();
    }

    public static class BookManagementProgram {
        private ArrayList<String> books;

        public BookManagementProgram() {
            books = new ArrayList<>();
        }

        public void addBook(String bookTitle) {
            books.add(bookTitle);
            System.out.println("Book added: " + bookTitle);
        }

        public void removeBook(String bookTitle) {
            if (books.remove(bookTitle)) {
                System.out.println("Book removed: " + bookTitle);
            } else {
                System.out.println("Book not found: " + bookTitle);
            }
        }

        public void viewBooks() {
            if (books.isEmpty()) {
                System.out.println("No books in the library.");
            } else {
                System.out.println("Books in the library:");
                for (String book : books) {
                    System.out.println(book);
                }
            }
        }
    }
}
```
