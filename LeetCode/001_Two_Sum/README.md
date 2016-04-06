# Two Sum

## Problem：

<div class="question-content">
 <p>
 </p>
 <p>
  Given an array of integers, find two numbers such that they add up to a specific target number.
 </p>
 <p>
  The function twoSum should return indices of the two numbers such that they add up to the target, where index1 must be less than index2. Please note that your returned answers (both index1 and index2) are not zero-based.
 </p>
 <p>
  You may assume that each input would have exactly one solution.
 </p>
 <p style="font-family:monospace">
  <b>
   Input:
  </b>
  numbers={2, 7, 11, 15}, target=9
  <br/>
  <b>
   Output:
  </b>
  index1=1, index2=2
 </p>
</div>

##My Result

First:  

```
    func twoSum(nums:[Int], _ target:Int) -> [Int] {
        var result:[Int] =  []
        for(var i = 0; i < nums.count; i++) {
            let first = nums[i]
            for (var j = i+1; j < nums.count; j++) {
                let second = nums[j]
                if (first + second == target) {
                    result = [i,j]
                } else {
                    print("Not Find")
                }
            }
        }
        return result
    }
```

Second:  

```
    func twoSumHashMap(nums:[Int], _ target: Int) -> [Int] {
        var result:[Int] = []
        var map:[Int:Int] = [:]
        for (index , x) in nums.enumerate() {
            let value = target - x
            if let anotherIndex = map[value] {
                result.append(anotherIndex)
                result.append(index)
                break
            } else {
                map[x] = index
            }
        }
        return result
    }
```

## Source:
[Leetcode](https://leetcode.com/problems/two-sum/)
