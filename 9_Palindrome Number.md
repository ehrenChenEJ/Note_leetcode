Given an integer x, return true if x is palindrome integer.

An integer is a palindrome when it reads the same backward as forward.

For example, 121 is a palindrome while 123 is not.
```php
class Solution {

    /**
     * @param Integer $x
     * @return Boolean
     */
    function isPalindrome($x) {
        // 不計入負數，十的倍數、零也不計入
        if ($x < 0 || $x%10 == 0 && $x!=0)
        {
            return false ;
        }
        // 需要比較的只有$x的前兩位，還有將最後面兩位倒換過來
        $Back  = 0 ;
        while($x>$Back)
        {
          $Back=$Back*10+$x%10;
          $x =intval(floor($x/10));
        }
        
        // 假如是奇數位的話
        // 第一位不需要做比較，所以是自己等於自己
        return $x==$Back || $x==intval(floor($Back /10));
    }
}
```