# improved-parakeet
import javax.swing.*; //JOptionPane

public class Teetop
{
    public static void main (String [] args)
    {
     int input;
     final int SENTINEL = -99;

     input = Integer.parseInt(JOptionPane.showInputDialog("Please enter integer value:"));

     while(input!=SENTINEL)
     {

     getSize(input);
     int[] intArray;
     intArray = new int[getSize(input)];
     fillArray(input,intArray);

     if(isPalindrome(intArray))
         JOptionPane.showMessageDialog(null, "This number is a Palindrome");
     else
         JOptionPane.showMessageDialog(null, "This number is NOT a Palindrome");
     
     input = Integer.parseInt(JOptionPane.showInputDialog("Please input integer value:"));
     }}

    public static int getSize(int num)
    {
        int count = 0;
        for (int i = num; i >=1;)
        {
             i = i/10;
             count++;
        }
        return count;
    }

    public static int[]fillArray(int num, int[] intArray)
    {
        int a = getSize(num);
        for (int i = a-1; i >=0;i--)
        {
             intArray [i] = num%10;
             num = num/10;
        }    
        return intArray;
    }

    public static boolean isPalindrome( int[] intArray )
    {
        int count = 0;
        for (int i:intArray)
        {
            count++;
        }
        int[] oppArray;
        oppArray = new int[count];
        for (int i = 0; i < count; i++)
        {
            oppArray[i]=intArray[count - i - 1];
        }
        for (int i=0; i<count; i++)
            {
            if(oppArray[i]!=intArray[i])
            return false;
            }
        return true;
    }
}
