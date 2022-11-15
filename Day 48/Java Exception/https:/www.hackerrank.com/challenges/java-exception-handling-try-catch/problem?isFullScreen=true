import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
    Scanner sc = new Scanner(System.in);
   
    
    try{
        //try block: operation to be performed 
        int a = sc.nextInt();
        int b = sc.nextInt();
        System.out.println(a/b);
        
    }catch(ArithmeticException | InputMismatchException e){
        //instance class used: 
        if( e instanceof ArithmeticException ){
        System.out.println(e);
        //java.lang.ArithmeticException: / by zero
    } else if ( e instanceof InputMismatchException){
        //System.out.println(e) //gives an error in one of the sample case: java.util.InputMismatchException: For input string: "2147483648"
        
        System.out.println("java.util.InputMismatchException");}
     }
    }
}
