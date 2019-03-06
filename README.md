## c#-deepcopy
Today I was doing an Array practice which requires me to reverse the order of all variables within an array which as shown below.

> int[] list1 = {1,2,3,4,5,6} --------> int[] list1 = {6,5,4,3,2,1}

I was thinking to create another array named as list2 and make it as a copy of list1, then reassign variables in list1 through list2.

> int[] list1 = {1,2,3,4,5,6};

>int[] list2 = list1;

>for(int i =0;i<list1.length;i++)

> {

>  list1[i] = list2[list1.length-i]; }
 
 However I found list2 would change its variables as well while list1 was being changed. So i searched online about this issue. It turns out that as array is a reference tpye,so if it is copied through "=", it is not actually copying the original variables to another array.In fact, the original one the copied one are sharing those variables. Then i found the method of CopyTo which can help to actually copy variables from one array to another. So i reedit my code as shown below.
 
 > int[] list1 = {1,2,3,4,5,6};

>int[] list2;

//The parameter of '0' sepecifys from which index you want to insert the copied variables.

>list2.Copyto(list1,0);

>for(int i =0;i<list1.length;i++)

> {

>  list1[i] = list2[list1.length-i]; 
   
  >}
  
