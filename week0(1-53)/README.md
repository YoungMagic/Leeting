# Week 0 7.17.2017

### 1. Two Sum
使用hash表，unordered_map,目标值减去数组里的数再在hash表中搜索，如找到即返回结果，否则将数组里的数添加进hash表

### 2. Add Two Numbers
*ListNode preHead（0）*创建新的链表，每个节点需要使用*new ListNode（）*，一个进位，还需判断下一个节点是否为0，返回*preHead.next*。

### 3. Longest Substring Without Repeating Characters
使用Hash表，当元素的计数不为0时重置，即需要一个Start，i-Start作为最大长度

### 5. Longest Palindromic Substring
从中间一点出发，过掉重复元素，然后向外扩散*s[j-1]==s[k+1]*,最大长度=*k-j+1*,返回*s.substr(start,maxLen)*。

### 6. ZigZag Conversion
用*numRows - 1*行来存储相应元素，最后将所以元素逐个相加。以*numRows - 1*为一个单位，*down*控制上下，当*row==numRows-2*时，*down=!down*

### 7. Reverse Integer
用*long long*型确保其不会溢出，*res = res * 10 + res % 10*。

### 8. String to Integer (atoi)
第一个不是空格开始，确定符号，数字大于0小于9则减去0得到数字，溢出同上。

### 9. Palindrome Number
双游标（一个除以10，一个除以100）获得右半边，判断奇偶

### 11. Container With Most Water
先以最宽为长计算面积，然后移动较小的那一根柱子

### 12. Integer to Roman
建立string table
|-------------------------------------------------------------|
|{"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII","IX"} | 
|{"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"} | 
|{"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"} | 
|{"","M", "MM", "MMM"}                                        |

再对号入座
                          

                
### 13. Roman to Integer
建立Hash表

| unordered_map<char, int> T  |
| --------------------------- |
| {'I', 1}                    |
| {'V',5}                     |
| {'X',10}                    |
| {'L',50}                    |
| {'C',100}                   |
| {'D',500}                   |
| {'M',1000}                  |

从末尾开始入座，若后项大于前项则减这项，否则加

### 14. Longest Common Prefix
最长的前缀长度等于这一项长度或者这一项不等于第一项的值时返回

### 15. 3Sum
先排序，使用双指针，for循环里用i定位，建立l,r双指针，如果得到结果，需要排除相同元素*if(i > 0 && (nums[i] == nums[i - 1])) continue*
                    
### 16. 3Sum Closest
排序，双指针，用*abs(target - curSum) < abs(target - clo)*表征距离，curSum是否大于target来决定指针移动方向

### 17. Letter Combinations of a Phone Number
cand存储下一个数字的字母，双for循环tmp临时存储结果，然后和result交换

### 18. 4Sum
sort,for,判断，**加速关键**如果最低四位大于target，break，如果nums[i] + 最大三位小于target，则continue。for，加速，判断，while，双指针，如果存在则push_back并且判断。

### 19. Remove Nth Node From End of List
一个二级指针指向头地址的地址，一个指针指向头指针，头指针先行，然后二级指针和头指针一起，最后*t1 = (*t1)->next。

### 20. Valid Parentheses
使用栈，switch，左边括号进栈右边出栈

### 21. Merge Two Sorted Lists
二级指针来移动链表，a.两个链表都不是NULL b.不是空的接下去。

### 22. Generate Parentheses
迭代法，二分，要么加*（*，要么加*）*，控制条件,left,right均为0时返回。

### 24. Swap Nodes in Pairs
二级指针移动，创建a,b指针用于交换，a指向c，b指向a，*pp = b.

### 26. Remove Duplicates from Sorted Array
用count来计数重复的数，如果不重复，则把不重复的数字往前放，nums[i - count] = nums[i].

###  27. Remove Element
同上

### 28. Implement strStr()
遍历数组，j来遍历needle,若j=size,则存在

### 29. Divide Two Integers
确定符号，确定溢出情况，被除数若大于除数，tmp等于除数，若被除数大于tmp×2，res+2,被除数-tmp,等等，res带上符号

### 31. Next Permutation
如果为逆排序，则反转然后返回。如果不是，从后找到第一个正排序组的前位，和向后找到第一个比这个数大的值，交换，逆排序之后的数

### 33. Search in Rotated Sorted Array
- If target is let's say 14, then we adjust nums to this, where "inf" means infinity:
  [12, 13, 14, 15, 16, 17, 18, 19, inf, inf, inf, inf, inf, inf, inf, inf, inf, inf, inf, inf]。

- If target is let's say 7, then we adjust nums to this:
  [-inf, -inf, -inf, -inf, -inf, -inf, -inf, -inf, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11]。
如果mid和target位于nums[0]同一边，则num取mid，否则取正或负无穷。

### 34. Search for a Range
二分查找
- 如果所有都刚好在区间内，返回区间
- 如果目标在区间内，二分查找，返回左右两个区间，若左区间为-1，则返回右区间，若右区间为-1，则返回左区间，若都不是，返回区间的并
- 返回空

### 35. Search Insert Position
二分查找用while，返回mid或者low 

### 36. Valid Sudoku
使用unordered_map<size_t, unordered_set<char>>数据结构建立三个map，分别为行，列，圈，如果插入失败，则false。为使[i][j]落入3*3网格，需使[i / 3 * 3 + j / 3]

### 38. Count and Say
循环，硬解。双for循环，使用迭代器来计数，最后要加上不同的项。

### 39. Combination Sum
递归。先排序，开始递归：
- 如果目标为0，则把之前的栈压入结果
- for循环，其中i=begin，如果目标大于元素，元素压栈，迭代，其中target = target - 元素，出栈，否则break。

### 40. Combination Sum II
类似上题，不过因为元素不能重复，加入if (i > start && num[i] == num[i-1]) continue;

### 43. Multiply Strings
双for循环，从末尾开始计算，设置一个进位变量，一个临时变量存储乘积+进位+本来的值（所有值应减去'0')。这个位的值=tmp%10+'0'，carry= tmp/10
