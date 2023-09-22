# ATM-
An atm project using java


package com.mycompany.atm;
import java.util.Scanner;
/**
 *
 * @author ajays
 */
public class Atm {
    static boolean logIn(String name,int pin,String user){
        if((name.equals(user))&& (pin==9898))
            return true;
        else return false;
        
    }
    static float deposit_Amount()
    {
              float deposit=0.0f;
              Scanner sc=new Scanner(System.in);
              System.out.print("Enter amount to be deposited");
              deposit=sc.nextFloat();
              System.out.print("Your amount "+deposit+" is deposited Successfully");
              return deposit;
    }
    static void withdraw_Amount()
    {
                float withdrawal=0.0f;
                Scanner sc=new Scanner(System.in);
               System.out.print("\n Enter withdrawal amount\n");
                 withdrawal=sc.nextFloat();
                 System.out.print("Your amount "+withdrawal+" is withdrawed successfully");
                 
    }
    static void check_Balance(String name,float bal){
        
    System.out.print("\n Dear "+name+" \n your balance is "+bal);
    }

    public static void main(String[] args) {
        String name;
        String user="Ajay Sharma";
        int pin;
        int choice;
        float bal=0.0f;
        Scanner sc=new Scanner(System.in);
        System.out.print("Enter user name\n");
        name=sc.nextLine();
        System.out.print("\nEnter your 4 digit pin\n");
        pin=sc.nextInt();
       if(logIn(name,pin,user))
       {
         System.out.print("\n Welcome To ATM service\n");
         System.out.print("\n1. Withdrawal \n2. Deposit \n3. Check Balance\n 4. Exit\n");
         System.out.print("Choose 1 for Withdrawal\n ");
         System.out.print("Choose 2 for deposit \n");
         System.out.print("Choose 3 for check balance\n ");
         System.out.print("Choose 4 to exit\n");
         choice=sc.nextInt();
         switch(choice)
         {
             case 1:withdraw_Amount();
             break;
             case 2: bal=deposit_Amount();
             break;
             case 3: check_Balance(name,bal);
             break;
             case 4:break;
         }
         
       }
       else
           System.out.print("Sorry! Unauthorized access");
        
    }
}
