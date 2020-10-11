#include <stdio.h>

unsigned long amount=5000, deposit, withdraw;
int choice, pin, k;
char transaction ='y';

void main()
{
	while (pin != 1520)
	{
		printf("PLEASE ENTER YOUR PIN NUMBER:");
		scanf("%d",&pin);
		if (pin != 1520)
		printf("PLEASE ENTER CORRECT PIN NUMBER\n");
	}
	do
	{
		printf("********Welcome to your bank*****************\n");
		printf("1. Check Balance\n");
		printf("2. Withdraw Cash\n");
		printf("3. Deposit Cash\n");
		printf("4. Quit\n");
		printf("*********************************************\n\n");
		printf("Please select your option: ");
		scanf("%d", &choice);
		switch (choice)
		{
		case 1:
			printf("\n YOUR BALANCE IN Rs : %lu ", amount);
			break;
		case 2:
			printf("\n ENTER THE AMOUNT TO WITHDRAW: ");
			scanf("%lu", &withdraw);
			if (withdraw % 100 != 0)
			{
				printf("\n PLEASE ENTER THE AMOUNT IN MULTIPLES OF 100");
			}
			else if (withdraw >(amount - 500))
			{
				printf("\n INSUFFICENT BALANCE");
			}
			else
			{
				amount = amount - withdraw;
				printf("\n\n PLEASE COLLECT YOUR CASH");
				printf("\n YOUR ACCOUNT CURRENT BALANCE IS%lu", amount);
			}
			break;
		case 3:
			printf("\n ENTER THE AMOUNT TO DEPOSIT");
			scanf("%lu", &deposit);
                        amount = amount + deposit;
			printf("YOUR ACCOUNT BALANCE IS %lu", amount);
			break;
		case 4:
			printf("\n THANKYOU");
			break;
		default:
			printf("\n INVALID CHOICE");
		}
		printf("\n\n\n DO YOU WANT TO HAVE ANOTHER TRANSCATION?(y/n): \n");
		fflush(stdin);
		scanf("%c", &transaction);
		if (transaction == 'n'|| transaction == 'N')
                    k = 1;
	} while (!k);
	printf("\n\n THANKYOU.");
}
