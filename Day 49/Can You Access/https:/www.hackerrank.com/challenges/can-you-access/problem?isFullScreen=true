import java.util.*;

public class Solution {

    static class Inner{


        private class Private{

            /**
             *powerof2 method.
             * @param num represent number
             * @return represents power of 2. if number is not power of 2, returns -1
             */
            private int powerof2(int num){
                int power=0;
                //First find is power of 2?
                //1 is power of 2^0=1
                if(num==1){
                    //That means 2^0=1, so its a 0 power of 2
                    return power;
                }
                else{
                    while (num%2==0){
                        num=num/2;
                        power++;
                    }
                    if(num==1){
                        //That means number is power of 2.
                    }
                    else
                    {
                        //That means left 3,5 etc. not power of 2.
                        power=-1;
                    }
                    return power;
                }
            }

        }



    }//end of Inner

    public static void main(String[] args) throws Exception {
        Scanner scanner = new Scanner(System.in);
        Inner inner = new Inner();
        Inner.Private innerPrivate = inner.new Private();
        int number = scanner.nextInt();
        int result = innerPrivate.powerof2(number);
        if(result==-1){
            System.out.println(number+" is not a power of 2");
        }
        else{
            System.out.println(number+" is power of 2");
            //System.out.println(result);
        }
        //An instance of class: Solution.Inner.Private has been created
        Object o = new Inner().new Private();
        System.out.println("An instance of class: " + o.getClass().getCanonicalName() + " has been created");
    }//end of main
}//end of Solution
