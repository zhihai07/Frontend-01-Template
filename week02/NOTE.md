# 第二周学习总结
## 语言按语法分类
#### 非形式语言
中文，英文
#### 形式语言（乔姆斯基谱系）
1. 0型 无限制文法
2. 1型 上下文相关文法
3. 2型 上下文无关文法
4. 3型 正则文法：能用正则表达式表示
###### 现代语言分为词法和语法部分（折中的办法）词法使用正则作一遍粗略的处理，把语言分成单个的词，把这些词作为输入流去做语法分析
## 产生式（BNF)
#### 用尖括号括起来的名称表示语法结构名
#### 语法结构分成基础结构和需要用其他语法结构定义的复合结构
1. 基础结构终结符
2. 复合结构称非终结符
#### 引号和中间的字符表示终结符可以有括号
#### *表示重复多次
#### |表示或
#### +表示至少一次

####  作业四则运算带括号括号 逻辑与或 产生式

```
<Number> ::= "0" | "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"
<DcimalNmber> ::= "0" | (("1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9")<Number>*)
<DcimalNmber> ::=/0|[1-9][0-9]*/  //正则预处理
<primaryExpression> ::= <DcimalNmber>|
    "(" <LogicalExpression> ")"
<AdditiveExpression> ::= <MultiplaicativeExpression> | 
    <AdditiveExpression> "+" <MultiplaicativeExpression> |
    <AdditiveExpression> "-" <MultiplaicativeExpression>
<MultiplaicativeExpression> ::= <DcimalNmber> |
    <MultiplaicativeExpression> "*" <DcimalNmber> |
    <MultiplaicativeExpression> "/" <DcimalNmber>
<LogicalExpression> ::= <AdditiveExpression> |
    <LogicalExpression> "||" <AdditiveExpression> |
    <LogicalExpression> "&&" <AdditiveExpression>
```



```
javaScript 产生式
AdditiveExpression：
MultiplaicativeExpression
AdditiveExpression + MultiplaicativeExpression
AdditiveExpression - MultiplaicativeExpression
```



## 通过产生式理解乔姆斯基谱系
#### 0型 无限制文法
- ？::=?
#### 1型 上下文相关文法
- ？<A>?::=?<B>? 问号是不变的 A  解释为 B
#### 2型 上下文无关文法
- <A>::=?
#### 3型 正则文法
- <A>::=<A>？
- <A>::=?<A>  这种是错误的

## 图灵完备性

#### 图灵完备性
##### 命令式---图灵机
- goto
- if和while
#### 声明式---lamba
- 递归

## 动态与静态

#### 动态
- 在用户的设备/在线服务器上
- 产品实际运行时
- Runtime
#### 静态
- 在程序员的设备上

## 类型系统

#### 动态类型系统与静态类型系统
##### 强类型与弱类型
- String + Number
- String == Boolean
- 复合类型
- 结构体
- 函数签名
- 子类型
- 逆变/协变

## 一般命令式编程语言
#### Atom  原子

#### Expression 表达式

#### statement   表达式

#### Structure   结构体
- Function
- Class
- Process
- Program  语法
- program
- Moudule
- Package
- Library

#### JavaScript

##### 语法——>语义——>运行时