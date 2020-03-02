## 1、两数之和

> 给定一个整数数组 nums 和一个目标值 target，请你在该数组中找出和为目标值的那 两个 整数，并返回他们的数组下标。你可以假设每种输入只会对应一个答案。但是，你不能重复利用这个数组中同样的元素。


示例:
```text
输入 nums = [2, 7, 11, 15], target = 9
输出 [0, 1]
```

- 解法1 - 暴力循环
  - 解题思路    
    2层循环，将原数组拆分为2个数相加 与 目标数组比较
    
  - 代码
    ```javascript
    /*
    * @param {number[]} nums
    * @param {number} target
    * @return {number[]}
    */
    var twoSum = function(nums, target) {
      const length = nums.length;
      if (length > 1) {
        for(let i=0;i<length;i++) {
          for (let j=i+1;j<length;j++) {
            if (nums[i]+nums[j] == target) {
              return [i,j];
            }
          } 
        }
      }
    };

    ```
    
  - 算法分析
    - 时间复杂度: `O(n^2)`
    - 空间复杂度: `O(1)`
    - 逻辑复杂度: `O(1)`


- 总结
  >解法1:
    - 1、初始设置一个空数组$result作为返回值，将条件符合的数组下标push进$result,break本次循环，break只可跳出一层循环，❌失败。
    - 2、第二层循环 let j=i+1; 💡j从i+1开始循环
    - 3、条件成立看到同学使用nums.indexOf(target - nums[i]) > -1方式，逆向思维🤚值得推荐