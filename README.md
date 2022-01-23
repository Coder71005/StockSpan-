# StockSpan-
Return an array with Stock Span for the consecutive no of days. 
For Example :  [100, 80, 60, 70, 60, 75, 85] , stock span [1, 1, 1, 2, 1, 4, 6].
  
  import java.util.*; 
  public class Stock Span{
 public static int[] StockSpan(int input[]) {
    	  if (input.length == 0){
    		   return input;
    	   } 
    	  Stack<Integer> stk = new Stack<>();
    	  stk.push(0); 
      int ans[] = new int[input.length];
    	  ans[0] = 1; 
      
      for(int i = 1 ; i < input.length;i++) {
          while(!stk.isEmpty() && input[i] > input[stk.peek()]) {
        	  stk.pop();
          }
          if(stk.isEmpty()) {
        	  ans[i] = i+1;
 
          }
          else {
        	  ans[i]= i-stk.peek();
        	  
          }
          stk.push(i); 
      }
      return ans; 
    	  
    
       }

public static void main(String[] args) {
		// TODO Auto-generated method stub
		Scanner sc = new Scanner (System.in); 
		int n = sc.nextInt(); 
		int arr[] = new int[n]; 
		for(int i = 0; i<n ;i++) {
			arr[i]= sc.nextInt(); 
		} 
		int []array  = StockSpan(arr); 
		for(int i =0; i<n;i++) {
			System.out.print(array[i]+ " ");
		}
		System.out.println();
		

	}
  } 

