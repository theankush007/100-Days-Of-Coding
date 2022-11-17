import java.util.*;
public class Main{
    
   static ArrayList func(ArrayList mylist){
      Iterator it=mylist.iterator();
      while(it.hasNext()){
         Object element =it.next();
         if(element instanceof Integer ||  "###".equals((String)element)){
             //Hints: use instanceof operator
             it.remove();
         }
      }
      return mylist;   
   }
   @SuppressWarnings({ "unchecked" })
   public static void main(String[] args){
      ArrayList mylist = new ArrayList();
      Scanner sc = new Scanner(System.in);
      int n = sc.nextInt();
      int m = sc.nextInt();
      for(int i = 0;i<n;i++){
         mylist.add(sc.nextInt());
      }
      
      mylist.add("###");
      for(int i=0;i<m;i++){
         mylist.add(sc.next());
      }
      
      ArrayList newList=func(mylist);
      Iterator it= newList.iterator();
      while(it.hasNext()){
         Object element = it.next();
         System.out.println((String)element);
      }
   }
}
