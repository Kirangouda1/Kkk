1.RESTUARENT BILLING PROJECT✔>>>>>>

import java.util.Scanner;

public class RestaurantBillingSystem {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int choice, quantity;
        double total = 0;

        System.out.println("================================");
        System.out.println("      RESTAURANT BILLING");
        System.out.println("================================");

        System.out.println("1. Burger      - Rs. 120");
        System.out.println("2. Pizza       - Rs. 250");
        System.out.println("3. Sandwich    - Rs. 100");
        System.out.println("4. Fried Rice  - Rs. 180");
        System.out.println("5. Coffee      - Rs.  50");
        System.out.println("6. Exit");

        while (true) {
            System.out.print("\nEnter your choice: ");
            choice = sc.nextInt();

            if (choice == 6) {
                break;
            }

            System.out.print("Enter quantity: ");
            quantity = sc.nextInt();

            switch (choice) {
                case 1:
                    total += 120 * quantity;
                    System.out.println("Burger added.");
                    break;

                case 2:
                    total += 250 * quantity;
                    System.out.println("Pizza added.");
                    break;

                case 3:
                    total += 100 * quantity;
                    System.out.println("Sandwich added.");
                    break;

                case 4:
                    total += 180 * quantity;
                    System.out.println("Fried Rice added.");
                    break;

                case 5:
                    total += 50 * quantity;
                    System.out.println("Coffee added.");
                    break;

                default:
                    System.out.println("Invalid choice!");
            }
        }

        System.out.println("\n================================");
        System.out.println("          FINAL BILL");
        System.out.println("================================");
        System.out.println("Total Amount : Rs. " + total);
        System.out.println("================================");
        System.out.println("Thank you! Visit again.");

        sc.close();
    }
}


2.TRAFFIC PROJECT✔>>>>>>

import java.util.Scanner;

public class TrafficSignal {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.println("===== TRAFFIC SIGNAL SYSTEM =====");
        System.out.println("1. Red Light");
        System.out.println("2. Yellow Light");
        System.out.println("3. Green Light");

        System.out.print("Enter signal number: ");
        int choice = sc.nextInt();

        switch (choice) {
            case 1:
                System.out.println("RED LIGHT - STOP");
                break;

            case 2:
                System.out.println("YELLOW LIGHT - WAIT");
                break;

            case 3:
                System.out.println("GREEN LIGHT - GO");
                break;

            default:
                System.out.println("Invalid signal number");
        }

        sc.close();
    }
}


3.BOOK MANAGEMENT SYSTEM>>>>>>

import java.util.Scanner;

public class BookManagementSystem {

    static String[] bookNames = new String[100];
    static int[] bookIds = new int[100];
    static int count = 0;

    static Scanner sc = new Scanner(System.in);

    // Add book
    static void addBook() {
        System.out.print("Enter Book ID: ");
        int id = sc.nextInt();
        sc.nextLine();

        System.out.print("Enter Book Name: ");
        String name = sc.nextLine();

        bookIds[count] = id;
        bookNames[count] = name;
        count++;

        System.out.println("Book added successfully!");
    }

    // Display books
    static void displayBooks() {
        if (count == 0) {
            System.out.println("No books available.");
            return;
        }

        System.out.println("\n--- Book List ---");

        for (int i = 0; i < count; i++) {
            System.out.println("Book ID: " + bookIds[i]);
            System.out.println("Book Name: " + bookNames[i]);
            System.out.println("--------------------");
        }
    }

    // Search book
    static void searchBook() {
        System.out.print("Enter Book ID to search: ");
        int id = sc.nextInt();

        for (int i = 0; i < count; i++) {
            if (bookIds[i] == id) {
                System.out.println("Book Found!");
                System.out.println("Book ID: " + bookIds[i]);
                System.out.println("Book Name: " + bookNames[i]);
                return;
            }
        }

        System.out.println("Book not found.");
    }

    // Delete book
    static void deleteBook() {
        System.out.print("Enter Book ID to delete: ");
        int id = sc.nextInt();

        for (int i = 0; i < count; i++) {
            if (bookIds[i] == id) {

                for (int j = i; j < count - 1; j++) {
                    bookIds[j] = bookIds[j + 1];
                    bookNames[j] = bookNames[j + 1];
                }

                count--;
                System.out.println("Book deleted successfully!");
                return;
            }
        }

        System.out.println("Book not found.");
    }

    // Main method
    public static void main(String[] args) {

        int choice;

        do {
            System.out.println("\n===== BOOK MANAGEMENT SYSTEM =====");
            System.out.println("1. Add Book");
            System.out.println("2. Display Books");
            System.out.println("3. Search Book");
            System.out.println("4. Delete Book");
            System.out.println("5. Exit");

            System.out.print("Enter your choice: ");
            choice = sc.nextInt();

            switch (choice) {
                case 1:
                    addBook();
                    break;

                case 2:
                    displayBooks();
                    break;

                case 3:
                    searchBook();
                    break;

                case 4:
                    deleteBook();
                    break;

                case 5:
                    System.out.println("Thank you!");
                    break;

                default:
                    System.out.println("Invalid choice!");
            }

        } while (choice != 5);

        sc.close();
    }
}

4.LIBRARY MANAGEMENT >>>>>>>>

import java.util.Scanner;

public class LibraryManagementSystem {

    static int[] bookId = new int[100];
    static String[] bookName = new String[100];
    static boolean[] issued = new boolean[100];
    static int count = 0;

    static Scanner sc = new Scanner(System.in);

    // Add book
    static void addBook() {
        System.out.print("Enter Book ID: ");
        int id = sc.nextInt();
        sc.nextLine();

        System.out.print("Enter Book Name: ");
        String name = sc.nextLine();

        bookId[count] = id;
        bookName[count] = name;
        issued[count] = false;
        count++;

        System.out.println("Book added successfully!");
    }

    // Display books
    static void displayBooks() {
        if (count == 0) {
            System.out.println("No books available.");
            return;
        }

        System.out.println("\n------ BOOK LIST ------");

        for (int i = 0; i < count; i++) {
            System.out.println("Book ID: " + bookId[i]);
            System.out.println("Book Name: " + bookName[i]);
            System.out.println("Status: " +
                    (issued[i] ? "Issued" : "Available"));
            System.out.println("---------------------");
        }
    }

    // Search book
    static void searchBook() {
        System.out.print("Enter Book ID: ");
        int id = sc.nextInt();

        for (int i = 0; i < count; i++) {
            if (bookId[i] == id) {
                System.out.println("Book Found!");
                System.out.println("ID: " + bookId[i]);
                System.out.println("Name: " + bookName[i]);
                System.out.println("Status: " +
                        (issued[i] ? "Issued" : "Available"));
                return;
            }
        }

        System.out.println("Book not found!");
    }

    // Issue book
    static void issueBook() {
        System.out.print("Enter Book ID to issue: ");
        int id = sc.nextInt();

        for (int i = 0; i < count; i++) {
            if (bookId[i] == id) {
                if (!issued[i]) {
                    issued[i] = true;
                    System.out.println("Book issued successfully!");
                } else {
                    System.out.println("Book is already issued!");
                }
                return;
            }
        }

        System.out.println("Book not found!");
    }

    // Return book
    static void returnBook() {
        System.out.print("Enter Book ID to return: ");
        int id = sc.nextInt();

        for (int i = 0; i < count; i++) {
            if (bookId[i] == id) {
                if (issued[i]) {
                    issued[i] = false;
                    System.out.println("Book returned successfully!");
                } else {
                    System.out.println("Book was not issued!");
                }
                return;
            }
        }

        System.out.println("Book not found!");
    }

    // Main method
    public static void main(String[] args) {
        int choice;

        do {
            System.out.println("\n===== LIBRARY MANAGEMENT SYSTEM =====");
            System.out.println("1. Add Book");
            System.out.println("2. Display Books");
            System.out.println("3. Search Book");
            System.out.println("4. Issue Book");
            System.out.println("5. Return Book");
            System.out.println("6. Exit");

            System.out.print("Enter your choice: ");
            choice = sc.nextInt();

            switch (choice) {
                case 1:
                    addBook();
                    break;

                case 2:
                    displayBooks();
                    break;

                case 3:
                    searchBook();
                    break;

                case 4:
                    issueBook();
                    break;

                case 5:
                    returnBook();
                    break;

                case 6:
                    System.out.println("Thank you for using Library System!");
                    break;

                default:
                    System.out.println("Invalid choice!");
            }

        } while (choice != 6);

        sc.close();
    }
}
