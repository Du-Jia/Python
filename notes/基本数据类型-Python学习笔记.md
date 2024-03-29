# Python学习笔记之基础数据类型（一）
## 数字类型
> 数字类型分为整数，浮点数，以及复数, 关系为 整数 -> 浮点数 -> 复数
### 整数类型
> 整数类型有四种进制表示
1. 十进制  不需要引导符号，直接按照习惯表示，例如1234， -89
2. 二进制  需要0b或者0B作为引导符号， 如0b0101，0B0101
3. 八进制 需要0o或者0O作为引导符号，如 0o711， 0O127
4. 十六进制 需要0x或者0X作为引导符号， 如0x100a, 0Xba11
***
### 浮点数类型
*浮点数的误差为0.0000000000000002，不能支持对精度需求比较高的高精度计算*
1. 一般记数方法：

0.0, -77., -2.17, 3.1416

2.科学记数法：
96e7, 4.3e-3, 9.6E5
*Python内置浮点数参数：sys.float_info(max=1.7976931348623157e+308, max_exp=1024, max_10_exp=308, min=2.2250738585072014e-308, min_exp=-1021, min_10_exp=-307, dig=15, mant_dig=53, epsilon=2.220446049250313e-16, radix=2, rounds=1)*
> 高精度浮点运算类型：Decimal
> Decimal 由标准库 decimal提供，可以使用getcontext().prec参数自定义浮点数精度的位数
实例如下：
```
>>> import decimal
>>> a = Decimal('3.1415926')
>>> a = decimal.Decimal('3.1415926')
>>> a
Decimal('3.1415926')
```

### 复数类型
* 复数类型的表示

实部用浮点数表示，虚部用浮点数加J或者j来表示，例如：
*2.0 \+ 3.0j*
> 可以使用`z.real`获得实部，使用`z.imag`获得虚部部分
示例：
```
>>> a.imag
3.0
>>> a
(2+3j)
>>> a.real
2.0
>>> a.imag
3.0
>>> 
```
* 复数类型的运算
> 复数类型的运算属于数学中复变函数的分支

## 数字类型的操作
### 内置的数值运算操作符
* \+, \-, \*, /, //, % , \*\* *其中//表示计算两个数的整数商， %计算余数*
#### 数值运算的规则
* 整数与浮点数运算结果是浮点数
* 浮点数与复数之间运算结果是复数
*数值运算的结果是生成更宽的类*

### 数值运算的内置函数
<table>
<tr>
<th>函数</th>
<th>描述</th>
</tr>
<tr>
<td>abs()</td>
<td>绝对值</td>
</tr>
<tr>
<td>divmod(x, y)</td>
<td>(x//y, x%y) （返回值是一个元祖）</td>
</tr>
<tr>
<td>pow(x, y[,z])</td>
<td>(x**y)%z （z可以省略） </td>
</tr>
<tr>
<td>round(x[,y])</td>
<td>四舍五入，保留y位小数</td>
</tr>
<tr>
<td>max(x1, x2, x3, ...)</td>
<td>最大值</td>
</tr>
<tr>
<td> min(x1, x2, x3, ...)</td>
<td>最小值</td>
</tr>
</table>
### 内置数字类型转换函数
* float(x)
* int(x)
* complex(x[,y])
*注意：上述函数参数中x可以是字符串或者数字，但y只能是整数或者浮点数*

## math库的使用
*math库不支持复数类型*
### 使用方法
1. 使用import导入库
采用`math.<b>()`的形式引用
*注意，这种方法导入之后只能使用上述方式引用函数*
2. 使用`from math import <functionName>` 或者 ` from math import *`形式
这种形式可以直接采用` functionName()`形式使用，后者可以使用库内所有函数
```
# 1.例如
>>>import math
>>>math.ceil(10.2)
11
# 2. 例如
>>>from math import *
>>>floor(10.2)
10
```
### math库
1. 包含4个数学常数
 * math.pi
 * math.e
 * math.inf *正无穷*
 * math.nan *非浮点数标记*
2. 数值表示函数
 * fabs(x): |x|
 * fmod(x, y): x % y
 * fsum([x, y, ...]): max in []
 * ceil(x): 
 * floor(x): 
 * factorial(x): x! 
 * gcd(a, b)
 * frepx(x): (m, e) *x = m \* 2 \* e*
 * ldexp(x, i): x \* 2 
 * modf(x): x的小数和整数部分
 * trunc(x): x的整数部分
 * copysign(x, y): \|x\| \* \|y\| / y *用数值y的正负号替换x的正负号*
 * isclose(a, b): True 或 False *比较a和b的相似性*
 * isfinite(x): True 或 False *x是否是无穷大*
 * isinf(x): True 或 False  * x是否是整数或者负无穷大*
 * isnan(x): True 或 False *x是否是NaN*
3. 幂对数函数
4. 三角运算函数
5. 高等特殊函数
