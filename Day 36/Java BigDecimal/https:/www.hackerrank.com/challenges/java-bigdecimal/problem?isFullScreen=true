import java.math.BigDecimal;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        
        ArrayList<String> numList = new ArrayList<String>();
        for(int i = 0 ; i < n ; i++) {
            numList.add(sc.next());
        }
        
        numList.sort((o1, o2) -> {
            int i = new BigDecimal(o1).compareTo(new BigDecimal(o2));
            return -i;
        });

        numList.forEach(( i)->System.out.println(i));
        
        sc.close();
    }
}
