### 48. Rotate Image
顺时针旋转，先将矩阵的行颠倒顺序，然后对称交换。逆时针选择，将矩阵的列颠倒顺序，然后对称交换

### 49. Group Anagrams
使用unordered_map，以排序好的单词作为键值，乱序的单词作为值。单词排序：建立数组count[26]=0,for循环，count[s[i] - 'a']++。接着建立单词大小的数组，初始化全为a，双for循环。

### 50. Pow(x, n)
分治策略，判断n的奇偶（和1与）,判断正负

### 54. Spiral Matrix
分上下左右方向，四个for循环，k为数组的下标，每次for循环后该方向+1，判断停止条件。

### 55. Jump Game
for循环，用reach记录可以到达的点， `reach = max(i + nums[i], reach)`。

### 56. Merge Intervals
首先对所有的间隙排列，判断后一个的start是否位于前一个的end位置。res.back().end。

### 58. Length of Last Word
使用while语句，不为空且n为正常值

### 59. Spiral Matrix II
while语句，四个方向一一计算，i,j作为索引，k作为值
