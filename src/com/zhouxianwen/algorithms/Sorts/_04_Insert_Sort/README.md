
  插入排序<br/>  
 <ul>  
 <li>从第一个元素开始，该元素可以认为已经被排序</li>  
 <li>取出下一个元素，在已经排序的元素序列中从后向前扫描</li>  
 <li>如果该元素（已排序）大于新元素，将该元素移到下一位置</li>  
 <li>重复步骤3，直到找到已排序的元素小于或者等于新元素的位置</li>  
 <li>将新元素插入到该位置中</li>  
 <li>重复步骤2</li>  
 </ul>  
 
 插入排序的基本思想是在遍历数组的过程中，假设在序号 i 之前的元素即 [0..i-1] 都已经排好序，本趟需要找到 i 对应的元素 x 的正确位置 k ，
 并且在寻找这个位置 k 的过程中逐个将比较过的元素往后移一位，为元素 x “腾位置”，最后将 k 对应的元素值赋为 x ，插入排序也是根据排序的特性来命名的。
 以下是一个实例，红色 标记的数字为插入的数字，被划掉的数字是未参与此次排序的元素，红色 标记的数字与被划掉数字之间的元素为逐个向后移动的元素，
 比如第二趟参与排序的元素为 [11, 31, 12] ，需要插入的元素为 12 ，但是 12 当前并没有处于正确的位置，于是我们需要依次与前面的元素 31 、 11 做比较，一边比较一边移动比较过的元素，
 直到找到第一个比 12 小的元素 11 时停止比较，此时 31 对应的索引 1 则是 12 需要插入的位置。
 初始：    [11, 31, 12, 5, 34, 30, 26, 38, 36, 18]  
   
 第一趟： [11, 31 , 12, 5, 34, 30, 26, 38, 36, 18] （无移动的元素）  
   
 第二趟： [11, 12 , 31, 5, 34, 30, 26, 38, 36, 18] （ 31 向后移动）  
   
 第三趟： [5 , 11, 12, 31, 34, 30, 26, 38, 36, 18] （ 11, 12, 31 皆向后移动）  
   
 第四趟： [5, 11, 12, 31, 34 , 30, 26, 38, 36, 18] （无移动的元素）  
   
 第五趟： [5, 11, 12, 30 , 31, 34, 26, 38, 36, 18] （ 31, 34 向后移动）  
   
 第六趟： [5, 11, 12, 26 , 30, 31, 34, 38, 36, 18] （ 30, 31, 34 向后移动）  
   
 第七趟： [5, 11, 12, 26, 30, 31, 34, 38 , 36, 18] （无移动的元素）  
   
 第八趟： [5, 11, 12, 26, 30, 31, 34, 36 , 38, 18] （ 38 向后移动）  
   
 第九趟： [5, 11, 12, 18 , 26, 30, 31, 34, 36, 38] （ 26, 30, 31, 34, 36, 38 向后移动）
 插入排序会优于选择排序，理由是它在排序过程中能够利用前部分数组元素已经排好序的一个优势，有效地减少一些比较的次数，当然这种优势得看数组的初始顺序如何，
 最坏的情况下（给定的数组恰好为倒序）插入排序需要比较和移动的次数将会等于 1 + 2 + 3… + n = n * (n + 1) / 2 ，这种极端情况下，插入排序的效率甚至比选择排序更差。
 因此插入排序是一个不稳定的排序方法，插入效率与数组初始顺序息息相关。一般情况下，插入排序的时间复杂度和空间复杂度分别为 O(n2 ) 和 O(1) 。