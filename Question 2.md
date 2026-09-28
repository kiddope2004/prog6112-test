public interface IConsoles {  
    String getConsoleType();  
    String getStore();  
    int getTotalSales();  
}  
  
public abstract class Consoles implements IConsoles {  
    // variables  
    protected String consoleType;  
    protected String storeName;  
    protected int totalSales;  
  
    // constructor  
    public Consoles(String consoleType, String storeName, int totalSales) {  
        this.consoleType = consoleType;  
        this.storeName = storeName;  
        this.totalSales = totalSales;  
    }  
  
    // getters - as required in question  
    @Override  
    public String getConsoleType() {  
        return consoleType;  
    }  
  
    @Override  
    public String getStore() {  
        return storeName;  
    }  
  
    @Override  
    public int getTotalSales() {  
        return totalSales;  
    }  
}  
  
  
  
public class ConsoleSales extends Consoles {  
  
    // constructor  
    public ConsoleSales(String consoleType, String storeName, int totalSales) {  
        super(consoleType, storeName, totalSales);  
    }  
  
    // method to print report  
    public void printReport() {  
        System.out.println("----------------------------------------");  
        System.out.println("NUMBER 1 ELECTRONICS SALES REPORT");  
        System.out.println("----------------------------------------");  
        System.out.println("Console Type: " + getConsoleType());  
        System.out.println("Store Name: " + getStore());  
        System.out.println("Total Sales: R" + getTotalSales());  
        System.out.println("----------------------------------------");  
    }  
}  
  
  
  
import java.util.Scanner;  
  
public class RunApplication {  
    public static void main(String[] args) {  
        Scanner input = new Scanner(System.in);  
  
        System.out.print("Enter console type (PS5 / XBOX / SWITCH): ");  
        String type = input.nextLine();  
  
        System.out.print("Enter store name: ");  
        String store = input.nextLine();  
  
        System.out.print("Enter total amount of sales: ");  
        int total = input.nextInt();  
  
        // Instantiate ConsoleSales class  
        ConsoleSales sale = new ConsoleSales(type, store, total);  
          
        // Print report  
        sale.printReport();  
    }  
}  
