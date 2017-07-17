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
