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

