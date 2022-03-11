# Summary of array

## 循环不变法则
左闭右开，左闭右闭 => Bisect, [Leetcode 59](https://leetcode.com/problems/spiral-matrix-ii/);

## 双指针，滑动窗口
有时候不一定在当前循环把所有问题解决，一次循环解决一个问题，下一个问题在下一循环解决更好；
[Leetcode 27] 
[Refernce](https://github.com/hzang41981/leetcode-master/blob/master/problems/0027.%E7%A7%BB%E9%99%A4%E5%85%83%E7%B4%A0.md)
```cpp
// 时间复杂度：O(n)
// 空间复杂度：O(1)
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        int slowIndex = 0;
        for (int fastIndex = 0; fastIndex < nums.size(); fastIndex++) {
            if (val != nums[fastIndex]) {
                nums[slowIndex++] = nums[fastIndex];
            }
        }
        return slowIndex;
    }
};
```

[Leetcode 209]
