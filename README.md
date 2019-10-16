9、leetcode415. 字符串相加
==
解法一：
--  
思路：
--
    使用连个指针，从后往前加，保留进位，当短的字符串到头时，使用‘0’代替。
代码： 
--
<pre>
/**
 * @author lihe
 * @date 2019/10/16 14:32
 * @descriptor  415. 字符串相加
 */
public class AddStrings_415 {
    public static String addStrings(String num1, String num2){
        StringBuilder builder = new StringBuilder();
        int sum = 0;
        int carry = 0;//carry:进位
        for (int i = num1.length()-1,j = num2.length()-1; i >= 0 || j >= 0 ; i--,j--) {
            sum = carry;
            sum += (i >= 0 ? num1.charAt(i) - '0' : 0);
            sum += (j >= 0 ? num2.charAt(j) - '0' : 0);
            builder.append(sum % 10);
            carry = sum / 10;
        }
        builder.append(carry == 1 ? 1 : "");
        return builder.reverse().toString();
    }

    public static void main(String[] args) {
        String s = addStrings("123", "789");
        System.out.println(s);
    }
}
<pre/>
