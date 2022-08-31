# squirrel-matrix-traversal
/* Online Java Compiler and Editor */
import java.util.*;
public class Main{

     public static void main(String []args){
       Scanner sc=new Scanner(System.in);
       int m=sc.nextInt();
       int n=sc.nextInt();
       int [][]arr=new int[m][n];
       for(int i=0;i<m;i++){
           for(int j=0;j<n;j++){
               arr[i][j]=sc.nextInt();
           }
       }
       int top=0;
       int right=n-1;
       int left=0;
       int bottom=m-1;
       int dir=0;
       while(top<=bottom && left<=right){
           if(dir==0){
               for(int i=left;i<=right;i++){
                   System.out.print(arr[top][i]+" ");
               }
               top++;
           }
           else if(dir==1){
               for(int j=top;j<=bottom;j++ ){
                   System.out.print(arr[j][right]+" ");
               }
               right--;
           }
           else if(dir==2){
               for(int i=right;i>=left;i--){
                   System.out.print(arr[bottom][i]+" ");
               }
               bottom--;
           }
           else{
               for(int j=bottom;j>=top;j--){
                   System.out.print(arr[j][left]+" ");
               }
               left++;
           }
           dir=(dir+1)%4;
       }
     }
}
