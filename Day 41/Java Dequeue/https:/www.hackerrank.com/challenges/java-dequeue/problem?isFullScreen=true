import java.util.*;
    public class test {
        public static void main(String[] args) {
            Scanner in = new Scanner(System.in);
            Deque<Integer> deque = new ArrayDeque<>();
            Set<Integer> set = new HashSet<>();
            int n = in.nextInt();
            int m = in.nextInt();
            int max = Integer.MIN_VALUE;

            for (int i = 0; i < n; i++) {
                int num = in.nextInt();
                deque.add(num);
                set.add(num);
                //size of the window
                // if we reach the size of the window
                if(i >= m-1) {
                  // once we add all to the set
                  // it should only have unics values
                  // in the window span
                  max = Math.max(max, set.size());                                     
                  int deq = deque.poll();
                  // delete the item wich will go out
                  // check in case a duplicate value still in the que we can not
                  // remove it from the stack if we did the next iteration
                  // it will be imbosible to add again the duplicate value
                  // because we can not re-iterate
                  if (!deque.contains(deq)){
                    set.remove(deq);                  
                  }                            
                }
               
            }
            System.out.println(max);
        }
    }
