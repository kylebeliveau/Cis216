// # Cis216
Java programming labs
package labexercise0;

import java.util.Scanner;
import java.text.DecimalFormat;

public class LabExercise0 {

    /* 
        Programmer: Kyle Beliveau
        Due Date:   Tuesday, January 30, 2018
        project Description: This program gets dimensions and pricing 
            information about a "sundae". These data elemtetns are used 
            to compute a price for the product. A summary of the results
            is displayed to the user.
        Project Number: 0(exercise)
    */
   
    public static void main(String[] args) {
        final double PI = 3.1415926;
        final int PRICE_MULITIPLIER = 2;
        
        //user supplied information
        String productName;
        double bottomDiameter, topDiameter, cupHeight, coneHeight;
        double pricePerOzIceCream, hotFudgeCanPrice, cupPrice, spoonPrice;
        int hotFudgeOzPerSundae, hotFudgeCanOz;
        
        //computer information
        double cupVolume, coneVolume, totalVolume;
        double iceCreamCost, hotFudgeCost, totalCost, tax, price;
        
        Scanner keyboard = new Scanner(System.in);
        DecimalFormat dollarFormat = new DecimalFormat("#0.00");
        
        //Get Product Dimensions
        System.out.println("Enter the name of the product.");
        productName = keyboard.nextLine();
        System.out.println("Enter the bottom diameter.");
        bottomDiameter = keyboard.nextDouble();
        System.out.println("Enter the top diameter.");
        topDiameter = keyboard.nextDouble();
        System.out.println("Enter the cup height.");
        cupHeight = keyboard.nextDouble();
        System.out.println("Enter the cone height.");
        coneHeight = keyboard.nextDouble();
        
        //Get Price Information
        System.out.println("Enter the price per ounce of ice cream.");
        pricePerOzIceCream = keyboard.nextDouble( );
        System.out.println("Enter the price for a can of hot fudge.");
        hotFudgeCanPrice = keyboard.nextDouble( );
        System.out.println("Enter the number of ounces in a can of hot fudge.");
        hotFudgeCanOz = keyboard.nextInt();
        System.out.println("Enter the number of ounces of hot fudge in "
                + " a sundae.:");
        hotFudgeOzPerSundae = keyboard.nextInt();
        System.out.println("Enter the price for a cup then a spoon.");
        cupPrice = keyboard.nextDouble();
        spoonPrice = keyboard.nextDouble();
        
        //Computer Ice Cream Used
        cupVolume = Math.pow((bottomDiameter/2.0 + topDiameter/2.0)/2.0,2)//avg
                * PI * cupHeight;
        coneVolume = 1.0/3.0 * Math.pow(topDiameter/2.0, 2) *coneHeight;
        totalVolume = cupVolume + coneVolume;
        
        //Compute Material Costs
        iceCreamCost = totalVolume * pricePerOzIceCream;
        hotFudgeCost = hotFudgeOzPerSundae * hotFudgeCanPrice / hotFudgeCanOz;
        totalCost = iceCreamCost + hotFudgeCost + cupPrice + spoonPrice;
        price = totalCost * PRICE_MULITIPLIER;
       
        //Display Cost Summary
        System.out.println("Product: " + productName);
        System.out.println("Ounces of ice cream in each sundae: " +
                totalVolume);
        System.out.println("Ice cream cost:  $" +
                dollarFormat.format(iceCreamCost));
        System.out.println("Hot fudge cost:  $" +
                dollarFormat.format(hotFudgeCost));
        System.out.println("Total cost:  $" + 
                dollarFormat.format(hotFudgeCost));
        System.out.println("Total cost:  $" + dollarFormat.format(totalCost));
        System.out.println("Price:  $" + dollarFormat.format(price));
    } // end main
    
} // end ClassExercise0 class
