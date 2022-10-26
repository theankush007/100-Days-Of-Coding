import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Adder a = new Adder();
        System.out.println("My superclass is: Arithmetic");
        a.call();
    }
}

class Arithmetic{
    int add(int a, int b){
        return  a+b;
    }
}
class Adder extends Arithmetic{
    void call(){
        System.out.print(add(40,2)+" ");
        System.out.print(add(10,3)+" ");
        System.out.print(add(10,10)+" ");
    }
}
