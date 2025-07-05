# credit-card-checker
 This is a beginner-friendly C program that analyzes a credit card number and determines its type (VISA, MASTERCARD, or AMEX) based on its length and starting digits. It does not use Luhn’s algorithm, but focuses on basic logic and control flow to practice conditional statements and string/number processing.  🛠️ Technologies Used Language: C  


#include <cs50.h>
#include <stdio.h>

  int main(void)
  {
      long num = get_long("Number: ");
      long n = num;
      int length = 0;

     while (n > 0)
     {
         n = n / 10;
         length++;
     }

     n = num;
     while (n >= 10000)
     {
         n = n / 10;
     }

     if ((n >= 3528 && n <= 3589) && length == 16)
     {
         printf("JCB\n");
     }
     else if ((n >= 2221 && n <= 5213) && length == 16)
     {
         printf("MASTERCARD\n");
     }
     else if ((n >= 300 && n <= 305) && length == 14)
     {
         printf("DINERS CLUB\n");
     }
     else if ((n == 36 || n == 38 || n == 39) && length == 14)
     {
         printf("DINERS CLUB\n");
     }
     else if ((n / 10 == 4) && (length == 13 || length == 16))
     {
         printf("VISA\n");
     }
     else if ((n == 34 || n == 37) && length == 15)
     {
         printf("AMEX\n");
     }
     else if ((n == 6011 || (n / 10 == 65) || (n >= 644 && n <= 649)) && length == 16)
     {
         printf("DISCOVER\n");
     }
     else if ((n >= 51 && n <= 55) && length == 16)
     {
         printf("MASTERCARD\n");
     }
     else
     {
         printf("INVALID\n");
     }
 }
