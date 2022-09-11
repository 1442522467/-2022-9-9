# 剑指 Offer 40. 最小的k个数
输入整数数组 `arr` ，找出其中最小的 `k` 个数。例如，输入4、5、1、6、2、7、3、8这8个数字，则最小的4个数字是1、2、3、4。
~~~
class  Solution {

public  int[] getLeastNumbers(int[] arr, int  k) {

PriorityQueue<Integer> pq=new  PriorityQueue<>(Collections.reverseOrder());

for(int  i=0;i<k;i++)

{

pq.add(arr[i]);

}

for(int  i=k;i<arr.length;i++)

{

if(!pq.isEmpty()&&arr[i]<pq.peek())

{

pq.remove();

pq.add(arr[i]);

}

}

int  res[]=new  int[k];

for(int  i=0;i<k;i++)

{

res[i]=pq.remove();

}

return res;

}

}
~~~
