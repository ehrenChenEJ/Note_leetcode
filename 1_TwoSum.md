# 1.Two Sum
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.
```php
class Solution {
    /**
     * @param Integer[] $nums
     * @param Integer $target
     * @return Integer[]
     */
    function twoSum($nums, $target) 
    {
        $res = [];
        for ($i = 0; $i <= count($nums);$i++)
        {
            $minus = $target - $nums[$i];
            
            // 對照key值有沒有減出來的值 
            if (array_key_exists($minus, $res)){
                return [$i, $res[$minus]];
            }
            else
            {
                // 沒有的話就把值塞進key
                $res[$nums[$i]] = $i;
            }
        }
        return [];
    }
}
```