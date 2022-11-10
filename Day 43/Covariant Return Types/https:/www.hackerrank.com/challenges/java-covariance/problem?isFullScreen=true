import java.io.*;
import java.util.*;

class Region{
    public  String yourNatioonalFlower(){
        return "Flower";
    }
}

class AndhraPradesh extends Region{
     public  String yourNatioonalFlower(){
        return "Lily";
    }
} 

class WestBengal extends Region{
     public  String yourNatioonalFlower(){
        return "Jasmine";
    }
} 


public class Solution {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
       Region r1 =null;
       String x= scan.next();
       switch(x){
          case "AndhraPradesh" : r1 = new AndhraPradesh(); break;
          case "WestBengal" : r1 = new WestBengal(); break;
       }
       
       System.out.println(r1.yourNatioonalFlower());
       
           }
}
