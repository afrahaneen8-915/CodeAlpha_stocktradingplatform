package code;
import java.util.ArrayList;
import java.util.Scanner;


class Stock {
    String stockName;
    double price;

    Stock(String stockName, double price) {
        this.stockName = stockName;
        this.price = price;
    }

    void displayStock() {
        System.out.println(stockName + " : ₹" + price);
    }
}


class Portfolio {
    ArrayList<String> stocksOwned = new ArrayList<>();
    double balance = 100000; // starting money

    void buyStock(Stock stock, int quantity) {
        double total = stock.price * quantity;

        if (balance >= total) {
            balance = balance - total;

            for (int i = 0; i < quantity; i++) {
                stocksOwned.add(stock.stockName);
            }

            System.out.println("Bought " + quantity + " shares of " + stock.stockName);
        } else {
            System.out.println("Not enough balance!");
        }
    }

    void sellStock(Stock stock, int quantity) {
        int count = 0;

        for (int i = 0; i < stocksOwned.size(); i++) {
            if (stocksOwned.get(i).equals(stock.stockName)) {
                stocksOwned.remove(i);
                i--;
                count++;

                if (count == quantity) {
                    break;
                }
            }
        }

        if (count > 0) {
            balance = balance + (stock.price * count);
            System.out.println("Sold " + count + " shares of " + stock.stockName);
        } else {
            System.out.println("You don't own this stock.");
        }
    }

    void showPortfolio() {
        System.out.println("\n----- Portfolio -----");
        System.out.println("Stocks Owned : " + stocksOwned);
        System.out.println("Available Balance : ₹" + balance);
    }
}

public class StockTradingPlatform {
	
	// Main Class
	

	    public static void main(String[] args) {

	        Scanner sc = new Scanner(System.in);

	       
	        Stock s1 = new Stock("TCS", 3500);
	        Stock s2 = new Stock("Infosys", 1500);
	        Stock s3 = new Stock("Reliance", 2800);

	        Portfolio user = new Portfolio();

	        int choice;

	        do {
	            System.out.println("\n===== STOCK TRADING PLATFORM =====");
	            System.out.println("1. Display Market Data");
	            System.out.println("2. Buy Stock");
	            System.out.println("3. Sell Stock");
	            System.out.println("4. View Portfolio");
	            System.out.println("5. Exit");
	            System.out.print("Enter your choice: ");

	            choice = sc.nextInt();

	            switch (choice) {

	                case 1:
	                    System.out.println("\n--- Market Data ---");
	                    s1.displayStock();
	                    s2.displayStock();
	                    s3.displayStock();
	                    break;

	                case 2:
	                    System.out.println("\nChoose Stock:");
	                    System.out.println("1. TCS");
	                    System.out.println("2. Infosys");
	                    System.out.println("3. Reliance");

	                    int buyChoice = sc.nextInt();

	                    System.out.print("Enter quantity: ");
	                    int qty = sc.nextInt();

	                    if (buyChoice == 1) {
	                        user.buyStock(s1, qty);
	                    } else if (buyChoice == 2) {
	                        user.buyStock(s2, qty);
	                    } else if (buyChoice == 3) {
	                        user.buyStock(s3, qty);
	                    } else {
	                        System.out.println("Invalid choice");
	                    }

	                    break;

	                case 3:
	                    System.out.println("\nChoose Stock:");
	                    System.out.println("1. TCS");
	                    System.out.println("2. Infosys");
	                    System.out.println("3. Reliance");

	                    int sellChoice = sc.nextInt();

	                    System.out.print("Enter quantity: ");
	                    int sellQty = sc.nextInt();

	                    if (sellChoice == 1) {
	                        user.sellStock(s1, sellQty);
	                    } else if (sellChoice == 2) {
	                        user.sellStock(s2, sellQty);
	                    } else if (sellChoice == 3) {
	                        user.sellStock(s3, sellQty);
	                    } else {
	                        System.out.println("Invalid choice");
	                    }

	                    break;

	                case 4:
	                    user.showPortfolio();
	                    break;

	                case 5:
	                    System.out.println("Thank You for Using the Platform!");
	                    break;

	                default:
	                    System.out.println("Invalid Option");
	            }

	        } while (choice != 5);

	        sc.close();
	    }
	}
