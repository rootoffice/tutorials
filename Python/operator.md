## 运算符
* 算术运算符
* 比较（关系）运算符
* 赋值运算符
* 逻辑运算符
* 位运算符
* 成员运算符
* 身份运算符

### 算术运算符
以下假设变量： a=10，b=20
<table class="reference">
<tbody>
<tr>
<th>运算符</th><th>描述</th><th>实例</th>
</tr>
<tr>
<td>+</td><td>加 - 两个对象相加</td><td> a + b 输出结果 30</td>
</tr>
<tr>
<td>-</td><td>减 - 得到负数或是一个数减去另一个数</td><td> a - b 输出结果 -10</td>
</tr>
<tr>
<td>\*</td><td>乘 - 两个数相乘或是返回一个被重复若干次的字符串</td><td> a * b 输出结果 200</td>
</tr>
<tr>
<td>/</td><td>除 - x除以y</td><td> b / a 输出结果 2</td>
</tr>
<tr>
<td>%</td><td>取模 - 返回除法的余数</td><td> b % a 输出结果 0</td>
</tr>
<tr>
<td>\***</td><td>幂 - 返回x的y次幂</td><td> a**b 为10的20次方， 输出结果 100000000000000000000</td>
</tr>
<tr>
<td>//</td><td>取整除 - 返回商的整数部分</td><td> 9//2 输出结果 4 , 9.0//2.0 输出结果 4.0</td>
</tr>
</tbody>
</table>

### 比较运算符
以下假设变量a为10，变量b为20
<table class="reference">
<tbody>
<tr>
<th width="10%">运算符</th><th>描述</th><th>实例</th>
</tr>
<tr>
<td>==</td><td> 等于 - 比较对象是否相等</td><td> (a == b) 返回 False。 </td>
</tr>
<tr>
<td>!=</td><td> 不等于 - 比较两个对象是否不相等</td><td> (a != b) 返回 true. </td>
</tr>
<tr>
<td>&lt;&gt;</td><td>不等于 -  比较两个对象是否不相等</td><td> (a &lt;&gt; b) 返回 true。这个运算符类似 != 。</td>
</tr>
<tr>
<td>&gt;</td><td> 大于 - 返回x是否大于y</td><td> (a &gt; b) 返回 False。</td>
</tr>
<tr>
<td>&lt;</td><td> 小于 - 返回x是否小于y。所有比较运算符返回1表示真，返回0表示假。这分别与特殊的变量True和False等价。注意，这些变量名的大写。</td><td> (a &lt; b) 返回 true。 </td>
</tr>
<tr>
<td>&gt;=</td><td> 大于等于	- 返回x是否大于等于y。</td><td> (a &gt;= b) 返回 False。</td>
</tr>
<tr>
<td>&lt;=</td><td> 小于等于 -	返回x是否小于等于y。</td><td> (a &lt;= b) 返回 true。 </td>
</tr>
</tbody></table>

### 赋值运算符
以下假设变量a为10，变量b为20
<table class="reference">
<tbody><tr>
<th>运算符</th><th>描述</th><th>实例</th>
</tr>
<tr>
<td>=</td><td>简单的赋值运算符</td><td> c = a + b 将 a + b 的运算结果赋值为 c</td>
</tr>
<tr>
<td>+=</td><td>加法赋值运算符</td><td> c += a 等效于 c = c + a</td>
</tr>
<tr>
<td>-=</td><td>减法赋值运算符</td><td> c -= a 等效于 c = c - a</td>
</tr>
<tr>
<td>\*=</td><td>乘法赋值运算符</td><td> c \*= a 等效于 c = c * a</td>
</tr>
<tr>
<td>/=</td><td>除法赋值运算符</td><td> c /= a 等效于 c = c / a</td>
</tr>
<tr>
<td>%=</td><td>取模赋值运算符</td><td> c %= a 等效于 c = c % a</td>
</tr>
<tr>
<td>\**=</td><td>幂赋值运算符</td><td> c \** = a 等效于 c = c ** a</td>
</tr>
<tr>
<td>//=</td><td> 取整除赋值运算符</td><td> c //= a 等效于 c = c // a</td>
</tr>
</tbody>
</table>

### 位运算符
<table class="reference">
<tbody>
<tr>
<th>运算符</th><th>描述</th><th>实例</th>
</tr>
<tr>
<td>&amp;</td><td>按位与运算符：参与运算的两个值,如果两个相应位都为1,则该位的结果为1,否则为0</td><td> (a &amp; b) 输出结果 12 ，二进制解释： 0000 1100</td>
</tr>
<tr>
<td>|</td><td> 按位或运算符：只要对应的二个二进位有一个为1时，结果位就为1。</td><td> (a | b) 输出结果 61 ，二进制解释： 0011 1101</td>
</tr>
<tr>
<td>^</td><td>按位异或运算符：当两对应的二进位相异时，结果为1 </td><td> (a ^ b) 输出结果 49 ，二进制解释： 0011 0001</td>
</tr>
<tr>
<td>~</td><td> 按位取反运算符：对数据的每个二进制位取反,即把1变为0,把0变为1 </td><td> (~a ) 输出结果 -61 ，二进制解释： 1100 0011， 在一个有符号二进制数的补码形式。</td>
</tr>
<tr>
<td>&lt;&lt;</td><td>左移动运算符：运算数的各二进位全部左移若干位，由"&lt;&lt;"右边的数指定移动的位数，高位丢弃，低位补0。</td><td> a &lt;&lt; 2 输出结果 240 ，二进制解释： 1111 0000</td>
</tr>
<tr>
<td>&gt;&gt;</td><td>右移动运算符：把"&gt;&gt;"左边的运算数的各二进位全部右移若干位，"&gt;&gt;"右边的数指定移动的位数 </td><td> a &gt;&gt; 2 输出结果 15 ，二进制解释： 0000 1111</td>
</tr>
</tbody>
</table>

### 逻辑运算符
以下假设变量 a 为 10, b为 20
<table class="reference">
<tbody>
<tr>
<th>运算符</th><th>逻辑表达式</th><th>描述</th><th>实例</th>
</tr>
<tr>
<td>and</td><td>x and y</td><td> 布尔"与" - 如果 x 为 False，x and y 返回 False，否则它返回 y 的计算值。	</td><td> (a and b) 返回 20。</td>
</tr>
<tr>
<td>or</td><td>x or y</td><td>布尔"或"	- 如果 x 是非0，它返回x的值，否则它返回y的计算值。</td><td> (a or b) 返回 10。</td>
</tr>
<tr><td>not</td><td>not x</td><td>布尔"非" - 如果x为True，返回False 。如果 x 为 False，它返回 True。</td><td> not(a and b) 返回 False </td>
</tr>
</tbody>
</table>

### 成员运算符
<table class="reference">
<tbody>
<tr>
<th>运算符</th><th>描述</th><th>实例</th>
</tr>
<tr>
<td>in</td><td>如果在指定的序列中找到值返回True，否则返回 False。</td>
<td>x在y序列中，如果x在y序列中返回True。</td>
</tr>
<tr>
<td>not in</td><td>如果在指定的序列中没有找到值返回True，否则返回False。</td>
<td>x不在y序列中,如果x不在y序列中返回True。</td>
</tr>
</tbody>
</table>

### 身份运算符
<table class="reference">
<tbody>
<tr>
<th>运算符</th><th>描述</th><th>实例</th>
</tr>
<tr>
<td>is</td><td>is是判断两个标识符是不是引用自一个对象</td><td><strong>x is y</strong>, 类似<strong>id(x) == id(y)</strong>,如果引用的是同一个对象则返回True，否则返回False</td>
</tr>
<tr>
<td>is not</td><td>is not是判断两个标识符是不是引用自不同对象</td><td><strong> x is not y</strong>，类似<strong>id(a) != id(b)</strong>。如果引用的不是同一个对象则返回结果True，否则返回False。</td>
</tr>
</tbody></table>


## 运算符优先级
<table>
<tbody>
<tr>
<th>运算符</th><th>描述</th>
</tr>
<tr>
<td>\*\*</td>
<td>指数 (最高优先级)</td>
</tr>
<tr>
<td>~ + -</td>
<td>按位翻转, 一元加号和减号 (最后两个的方法名为 +@ 和 -@)</td>
</tr>
<tr>
<td>\* / % //</td>
<td>乘，除，取模和取整除</td>
</tr>
<tr>
<td>+ -</td>
<td>加法减法</td>
</tr>
<tr>
<td>&gt;&gt; &lt;&lt;</td>
<td>右移，左移运算符</td>
</tr>
<tr>
<td>&amp;</td>
<td>位 'AND'</td>
</tr>
<tr>
<td>^ |</td>
<td>位运算符</td>
</tr>
<tr>
<td>&lt;= &lt; &gt; &gt;=</td>
<td>比较运算符</td>
</tr>
<tr>
<td>&lt;&gt; == !=</td>
<td>等于运算符</td>
</tr>
<tr>
<td>= %= /= //= -= += \*= \*\*=</td>
<td>赋值运算符</td>
</tr>
<tr>
<td>is is not</td>
<td>身份运算符</td>
</tr>
<tr>
<td>in not in</td>
<td>成员运算符</td>
</tr><tr>
<td>not or and</td>
<td>逻辑运算符</td>
</tr>
</tbody>
</table>
