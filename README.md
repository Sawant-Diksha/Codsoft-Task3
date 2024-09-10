# Codsoft-Task3


import java.util.Scanner;

class Customer
{

    double bank_balance = 0.0;
	void customer_balence(double balance)
	{
		this.bank_balance = bank_balance+balance;
    }

    void current_balence()
	{
        System.out.println("YOUR CURRENT BANK BALENCE IS :-"+bank_balance+"Rs");
    }
 
}

class AtmMachine extends Customer 
{
    Scanner sc = new Scanner(System.in);
	
	void deposite_amount() 
	{

        System.out.println("ENTER A AMOUNT FOR DEPOSITE :-");
        double deposite_amount = sc.nextDouble();

        if(deposite_amount<=99)
		{
            System.out.println("PLEASE ENTER AMOUNT ABOVE 100 RUPEES");
            deposite_amount();
        }
        else
		{

            System.out.println("AMOUNT DEPOSITED SUCCESSFULLY..");
              customer_balence(deposite_amount);   
        }

    }
	void withdraw_amount() 
	{
		System.out.println("ENTER AMOUNT TO WITHDRAW FROM ("+bank_balance+")Rs :-");
        int input_amount = sc.nextInt();
        if(input_amount>=100)
		{

            if(input_amount>bank_balance)
			{
                System.out.println("SORRY YOUR BANK BALENCE IS NOT SUFFICIENT!!!!!....");
			}
            else
			{
                bank_balance = bank_balance-input_amount;
                System.out.println("MONEY IS WITHDRAWED SUCCESSFULLY..");
            }

        }
        else
		{
            System.out.println("ENTER A AMOUNT ABOVE 100 RS.");
        }

    }

	void check_balance() 
	{
		if (bank_balance>=100)
		{
			current_balence();
			
		}
		else
			System.out.println("SORRY YOUR BANK BALANCE IS NOT ENOUGH TO SHOW...");
			
		
    }

}

class Task3
{

    public static void main(String []args)
	{

        Scanner sc = new Scanner(System.in);
        AtmMachine Atm = new AtmMachine();
		System.out.println("(.....YOUR INTIAL BANK BALENCE IS NOT ENOUGHT TO WITHDRAW PLEASE FIRST DEPOSITE SOME AMOUNT....)");

        char character;
		aa:
        do{
			System.out.println("===============================================================================================");
			System.out.println("\tTO DEPOSITE AMOUNT PRESS :-1");
            System.out.println("\tTO WITHDRAW AMOUNT PRESS :-2");
            System.out.println("\tTO CHECK BALANCE PRESS   :-3");
			System.out.println("\tTO TAKE EXIT PRESS       :-4");
			System.out.println("===============================================================================================");
            System.out.println("\nENTER A OPTION :-");

            int x = sc.nextInt();

            switch (x)
			{
                case 1: 
                    Atm.deposite_amount();
					break;
					
                case 2:
                    Atm.withdraw_amount();
					break;
        
                case 3: 
                    System.out.println("CHECK YOUR BALANCE HERE");
                    Atm.check_balance();
					break;
				case 4:
					System.out.println("THANK YOU!!!....");
					break aa;
                default:
                    System.out.println("PLEASE ENTER VALID OPTION");
					break;
             
            }
			System.out.println("===============================================================================================");
			System.out.println("\nDO YOU WANT TO CONTINUE TRANSACTION[YES/NO]....");
            character = sc.next().charAt(0);
        
        }while(character == 'Y' || character == 'y');

    }
}
