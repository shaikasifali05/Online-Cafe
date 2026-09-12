# Online-Cafe
A simple Online Cafe billing system developed using Java.

import java.util.Scanner;

public class online_cafe {

    static int bill = 0;

    
    public static void menu() {

        System.out.println("\n========== OUR CAFE MENU ==========");

        System.out.println("\n----- HOT BEVERAGES -----");
        System.out.println("1.  Coffee             ₹59");
        System.out.println("2.  Cappuccino         ₹99");
        System.out.println("3.  Espresso           ₹79");
        System.out.println("4.  Latte              ₹109");
        System.out.println("5.  Hot Chocolate      ₹119");
        System.out.println("6.  Tea                ₹29");
        System.out.println("7.  Green Tea          ₹49");
        System.out.println("8.  Masala Tea         ₹39");
        System.out.println("9.  Ginger Tea         ₹39");

        System.out.println("\n----- FAST FOOD -----");
        System.out.println("10. Chicken Burger     ₹199");
        System.out.println("11. Veg Burger         ₹149");
        System.out.println("12. Cheese Burger      ₹179");
        System.out.println("13. Pizza              ₹199");
        System.out.println("14. French Fries       ₹99");
        System.out.println("15. Cheese Fries       ₹129");
        System.out.println("16. Sandwich           ₹129");
        System.out.println("17. Pasta              ₹159");
        System.out.println("18. Garlic Bread       ₹99");

        System.out.println("\n19. View Bill");
        System.out.println("20. Exit");

        System.out.println("===================================");
    }

    
    public static void customerChoice(int choice, Scanner sc) {

        String itemName = "";
        int price = 0;

        switch (choice) {

            
            case 1:
                itemName = "Coffee";
                price = 59;
                break;

            case 2:
                itemName = "Cappuccino";
                price = 99;
                break;

            case 3:
                itemName = "Espresso";
                price = 79;
                break;

            case 4:
                itemName = "Latte";
                price = 109;
                break;

            case 5:
                itemName = "Hot Chocolate";
                price = 119;
                break;

            case 6:
                itemName = "Tea";
                price = 29;
                break;

            case 7:
                itemName = "Green Tea";
                price = 49;
                break;

            case 8:
                itemName = "Masala Tea";
                price = 39;
                break;

            case 9:
                itemName = "Ginger Tea";
                price = 39;
                break;

            
            case 10:
                itemName = "Chicken Burger";
                price = 199;
                break;

            case 11:
                itemName = "Veg Burger";
                price = 149;
                break;

            case 12:
                itemName = "Cheese Burger";
                price = 179;
                break;

            case 13:
                itemName = "Pizza";
                price = 199;
                break;

            case 14:
                itemName = "French Fries";
                price = 99;
                break;

            case 15:
                itemName = "Cheese Fries";
                price = 129;
                break;

            case 16:
                itemName = "Sandwich";
                price = 129;
                break;

            case 17:
                itemName = "Pasta";
                price = 159;
                break;

            case 18:
                itemName = "Garlic Bread";
                price = 99;
                break;

            
            case 19:
                showBill();
                return;

            
            case 20:
                System.out.println("\nThank you for visiting our cafe!");
                return;

            default:
                System.out.println("\nInvalid choice! Please select 1-20.");
                return;
        }

        
        System.out.print("How much quantity do you want: ");
        int quantity = sc.nextInt();

        if (quantity <= 0) {
            System.out.println("Quantity must be greater than 0.");
            return;
        }

        int itemTotal = quantity * price;
        bill += itemTotal;

        System.out.println("\n" + quantity + " x " + itemName
                + " ordered successfully!");

        System.out.println("Item Total: ₹" + itemTotal);
        System.out.println("Current Bill: ₹" + bill);
    }

    
    public static void showBill() {

        System.out.println("\n************************************");
        System.out.println("              YOUR BILL");
        System.out.println("************************************");
        System.out.println("Total Amount: ₹" + bill);
        System.out.println("************************************");
    }

    
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.println("====================================");
        System.out.println("        WELCOME TO OUR CAFE");
        System.out.println("====================================");

        while (true) {

            menu();

            System.out.print("ORDER PLEASE: ");
            int order = sc.nextInt();

            if (order == 20) {

                System.out.println("\n************************************");
                System.out.println("       THANK YOU! VISIT AGAIN!");
                System.out.println("       Your Final Bill: ₹" + bill);
                System.out.println("************************************");

                break;
            }

            customerChoice(order, sc);
        }

        sc.close();
    }
}

