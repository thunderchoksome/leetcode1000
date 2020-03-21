#LEETCODE-EASY20-有效的括号
***
给定一个只包括 '('，')'，'{'，'}'，'['，']' 的字符串，判断字符串是否有效。

有效字符串需满足：

左括号必须用相同类型的右括号闭合。
左括号必须以正确的顺序闭合。
注意空字符串可被认为是有效字符串。

示例 1:

输入: "()"
输出: true
示例 2:

输入: "()[]{}"
输出: true
示例 3:

输入: "(]"
输出: false
示例 4:

输入: "([)]"
输出: false
示例 5:

输入: "{[]}"
输出: true

***
##本小白代码：
```

	class Solution {
	    public boolean isValid(String s) {
	       if(s.length()==0)return true;
	       if(s.length()==1)return false;
	       char[] arr=new char[s.length()];
	       int j=0;
	       for(int i=0;i<s.length();i++){
	           switch(s.charAt(i)){
	               case '(':arr[j]='(';j++;break;
	               case '[':arr[j]='[';j++;break;
	               case '{':arr[j]='{';j++;break;
	               case ')':
	                        if(j>=1&&arr[j-1]=='('){
	                            arr[j-1]='a';
	                            j--;
	                        }else return false;
	                        break;
	               case ']':
	                        if(j>=1&&arr[j-1]=='['){
	                            arr[j-1]='a';
	                            j--;
	                        }else return false;
	                        break;
	               case '}':
	                        if(j>=1&&arr[j-1]=='{'){
	                            arr[j-1]='a';
	                            j--; 
	                        }else return false;
	                        break;
	           }
	       } 
	       if(j==0)
	        return true;
	        return false;
	    }
	}

```

执行用时 :
1 ms
, 在所有 Java 提交中击败了
98.98%
的用户（还行）

内存消耗 :
37.6 MB
, 在所有 Java 提交中击败了
5.03%
的用户（裂开）

一开始我的想法错了，想直接用索引和符号一个个对位，然后发现自己搞得太复杂了，然后想了一下用两个数组去保存左括号和右括号再去做，结果又犯错了，尝试很多次之后才发现用栈的方式就可以，最后卡在了变量j的处理上面，因为我采用数组来取代栈，对于数组索引j的范围把控不好，最后尝试很多遍才写出来。
学海无涯苦作舟呀呀呀呀~