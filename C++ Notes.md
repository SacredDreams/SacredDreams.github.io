# 目录
  - [001 输入输出与基本数学计算](https://github.com/SacredDreams/C-Notes/blob/main/README.md#001-输入输出与基本数学计算)
  - [002 数据类型](https://github.com/SacredDreams/C-Notes/blob/main/README.md#002-数据类型)
  - [003 if语句](https://github.com/SacredDreams/C-Notes/blob/main/README.md#003-if语句)
  - [004 循环](https://github.com/SacredDreams/C-Notes/blob/main/README.md#004-循环)
  - [005 文件的写入和读取](https://github.com/SacredDreams/C-Notes/blob/main/README.md#005-文件的写入和读取)
  - [006 数组](https://github.com/SacredDreams/C-Notes/blob/main/README.md#006-数组)


# 001 输入输出与基本数学计算
 [[返回目录]](https://github.com/SacredDreams/C-Notes/blob/main/README.md#目录)  

**1. 输出样例**
```C++
#include <iostream> // 输入输出

using namespace std;

int main(){
  	// 输出字符串
  	cout << "hello world" << endl; // 末尾endl用来换行，也可写作“cout << "hello world";”，即没有换行
  
  	// 输入字符
  	char ch;
  	cin >> ch; // g 注意：若输入为数字，则输出为数字字符，而非数字
  	cout << ch << endl; // g
  
  	// 输出一个金字塔
  	cout << "     *" << endl;
  	cout << "    ***" << endl;
  	cout << "   *****" << endl;
  	cout << "  *******" << endl;
  	cout << " *********" << endl;
  	cout << "***********" << endl;

  	return 0; // 程序结束
}
```

**2. 数学计算样例**
```c++
#include <iostream>
#include <cmath> // 数学计算
#include <iomanip> // 保留小数位数

using namespace std;

int main(){
  	// 进行数学计算
  	int a = 20, b = 10;
  	double c = 5.22, d = 4.82;
  	
  	cout << a + b << endl; // 30
  	cout << a - b << endl; // 10
  	cout << a * b << endl; // 200
  	cout << a / b << endl; // 2
  	cout << 10 / 3 << endl; // 3 注意：计算结果舍弃小数点后所有数字，保留整数部分
  	cout << a % b << endl; // 0
  	cout << 10 % 3 << endl; // 1
  	
  	cout << c + d << endl; // 10.4
  	cout << c * d << endl; // 25.1604 默认6位
  	cout << c / d << endl; // 1.08299 默认6位
	
  	cout << pow(2, 3) << endl; // 8 平方运算 注意：在接近临界值的时候，避免使用pow()函数
  	cout << sqrt(10000) << endl; // 100 开方运算
  	cout << abs(-2) << endl; // 2 绝对值运算
  	
  	cout << fixed << setprecision(5) << c << endl; // 5.22000 保留五位小数
  	
  	return 0;
}
```

**3. 拿取各个数位数字**
```c++
#include <iostream>

using namespace std;

int main(){
  	int number = 123;
	
  	cout << number / 100 << endl; // 拿取百位
  	cout << number % 100 / 10 << endl; // 拿取十位
  	cout << number / 10 % 10 << endl; // 拿取十位
  	cout << number % 10 << endl; // 拿取个位
  	return 0;
}
```

**4. 交换两变量数据**
```c++
#include <iostream>

using namespace std;

int main(){
	int a = 1, b = 2;
  	int c = 3, d = 4;
  	int e = 5, f = 6;
  	int temp;
  
  	// 方法一
	temp = a;
  	a = b;
  	b = temp;
  	cout << a << ' ' << b << endl;
	
  	// 方法二
  	c += d; // c == 7
  	d = c - d; // d == 3
  	c -= d; // c == 4
  	cout << c << ' ' << d << endl;
	
  	// 方法三
  	swap(e, f);
  	cout << e << ' ' << f << endl;
  	
  	return 0;
}
```
# 002 数据类型
 [[返回目录]](https://github.com/SacredDreams/C-Notes/blob/main/README.md#目录)  

**1. 数据类型**
```c++
#include <iostream>

using namespace std;

int main(){
	/*
	short 短整型          -32768 ~ 32767         有效位数：5     占用字节：2
	int 基本整形          -2^31 ~ (2^31)-1       有效位数：10    占用字节：4
	long long 长整型      -2^63 ~ (2^63)-1       有效位数：19    占用字节：8
    	flaat 单精度浮点型    -3.4e-38 ~ 3.4e+38     有效位数：7     占用字节：4
	double 双精度浮点型   -1.7e-308 ~ 1.7e+308   有效位数：15    占用字节：8
	long double 扩展双精度型
    	char 字符型           256个不同字符                          占用字节：1
    	bool 布尔型(True/False)
    	const	常量
  	*/
	
  	/*
  	ASCII码表(举例)
	0	48
	1	49
	2	50
	......
	A	65
	B	66
	C	67
	......
	Z	90
	a	97
	b	98
	......
	*/
  	
  	// int 类型
	int max_i, min_i;
  	
	max_i = 2147483647; // int最大值
	min_i = -2147483648; // int最小值
	max_i ++;
	min_i --;
	cout << max_i << endl << min_i << endl; // -2147483648 2147483647
	
	// long long 类型
	long long max_ll, min_ll;
	max_ll = 9223372036854775807;
	min_ll = -9223372036854775808;
	max_ll ++;
	min_ll --;
	cout << max_ll << endl << min_ll << endl; // -9223372036854775808 9223372036854775807
  	
  	// double 类型
  	double d1 = 0.123456789, d2 = 123456789.123456789012345;
  	cout << d1 << endl << d2 << endl; // 0.123457 1.23457e+008
  	
  	// float 类型
  	float f = 3.14f;
  	cout << f << endl; // 3.14
  	
  	// char 类型
  	char c = 'c';
  	cout << c << endl; // c
  	
  	// bool 布尔值
  	bool b1 = 0, b2 = 1, b3 = 2;
  	bool b4 = true, b5 = false;
  	cout << b1 << endl << b2 << endl << b3 << endl << b4 << endl << b5 << endl; // 0 1 1 1 0 注意：转换时，true为1，False为0；0为false，其余数字均为true
  	
  	// const 常量
  	const int value = 1; // 或者“int const value = 1;”，但切忌使用“value ++;”等操作改变其值
  	cout << value << endl; // 1
  	
  	// 使用sizeof()函数计算占用字节
  	short s = 12;
  	int i = 12;
  	cout << sizeof(s) << endl << sizeof(i) << endl; // 2 4
  	
  	return 0;
}
```
**2. 数据类型转换**
```c++
#include <iostream>

using namespace std;

int main(){
  	// 数据类型隐式转换
  	/*
	char + short = int → long long
	float + double = double
	*/
  	char t_1 = 'a'; short t_2 = 100; int t_3 = 200; long long t_4 = 12345; double t_5 = 1.123456;
	cout << t_1 + t_2 << endl; // 197
  	cout << t_2 + t_3 << endl; // 300
  	cout << t_3 + t_4 << endl; // 12345
  	cout << t_4 + t_5 << endl; // 12346.1
  	cout << t_5 + t_1 << endl; // 98.1235
  	
  	// 数据类型强制转换
  	double d1 = 3.1415926, d2 = 2.7182818;
  	cout << (int)d1 << endl << int(d2) << endl; // 3 2
  	
  	return 0;
}
```
# 003 if语句
 [[返回目录]](https://github.com/SacredDreams/C-Notes/blob/main/README.md#目录)  

**1. 单层判断**
```c++
#include <iostream>

using namespace std;

int main(){
  	// 简单的if判断
  	/*
	当if中的内容成立，即为true时，执行内部代码，若不成立，即为false，则直接跳过
  	*/
  	int num1;
  	cin >> num1;
  	
  	if(num1 == 0){
		cout << "数字为0" << endl;
  	}
  	// 利用true或false判断，还可写为：
  	if(!num1){ // 叹号“!”表示取反，num1本身为整形0，转换成bool后为false，为了使条件成立，需要进行取反操作，使其变为true
  	  	cout << "数字为0" << endl;
  	}
  	if(num1 > 0){ // 取反“if(!(num1 > 0))”意思为“if(num1 <= 0)”
  	  	cout << "数字大于0" << endl;
  	}
  	if(num1 < 0){ // 取反与上方同理
		cout << "数字小于0" << endl;
  	}
  	
  	// 添加“否则”
  	int num2;
  	cin >> num2;
  	
  	if(!num2){
	  	cout << "数字为0" << endl;
  	}else{
    		cout << "数字不为0" << endl;
  	}
  	
  	// 添加多条判断
  	int num3;
  	cin >> num3;
  	
  	if(!num3){
    		cout << "数字为0" << endl;
  	}else if(num3 == 1){
    		cout << "数字为1" << endl;
  	}else{
    		cout << "数字既不是0，也不是1" << endl;
  	}
  	
  	return 0;
}
```
**2. 嵌套判断**
```c++
#include <iostream>

using namespace std;

int main(){
  	int num1;
  	cin >> num1;
  	
  	if(num1 <= 10){ // 判断小于等于10的数字
    		if(num1 % 2 == 0){
      			cout << "偶数" << endl;
    		}else{
      			cout << "奇数" << endl;
    		}
  	}else if(num1 <= 20){ // 判断大于10小于等于20的数字
    		if(num1 % 2){ // 如果取余2的结果为0（说明是偶数），那么是false，则不执行，如果取余2的结果不为0（说明是奇数），为true，则执行
      			cout << "奇数" << endl;
    		}else{
      			cout << "偶数" << endl;
    		}
  	}
  	
  	return 0;
}
```
# 004 循环
 [[返回目录]](https://github.com/SacredDreams/C-Notes/blob/main/README.md#目录)  

**1. 前++、--与后++、--**
```c++
#include <iostream>

using namespace std;

int main(){
	int a = 0;
	
	cout << a << endl; // 0000
	cout << a ++ << endl; // 0 先输出后++
	cout << ++ a << endl; // 1 先++后输出
	cout << a -- << endl; // 0 先输出后--
	cout << -- a << endl; // -1 先--后输出
	
	return 0;
}
```
**2. while循环**
```c++
#include <iostream>

using namespace std;

int main(){
	// 输出0 ~ 100
	int num1 = 0;
	
	while(num1 <= 100){ // 当num满足条件时才执行
		cout << num1 << endl;
		num1 ++; // 随着num的增加，当num加到101时，不满足条件，则跳出循环
	}
	
	// 死循环
	while(true){
		cout << "这是一个死循环！！！" << endl;
	}
	
	// 输入任意数字，如果为0则跳出循环，如果不为0，则输出该数字
	while(true){
		int num2;
		cin >> num2;
		if(!num2){
			break; // 使用break跳出循环
		}
	}
	
	// 遍历0 ~ 100之间的数，如果这个数是偶数，则输出“偶数”，不是则跳过
	int num3 = -1;
	while(num3 < 101){ // 或写作“num3 <= 100”
		num ++;
		if(num % 2){
			continue; // 结束当次循环，直接进入下一次循环
		}
		cout << "偶数" << endl;
	}
	
	return 0;
}
```
**3. do-while循环**
```c++
#include <iostream>

using namespace std;

int main(){
	// 先执行do中的内容，再判断是否需要循环do中的内容
	
	// 输入一个数n，输出0 ~ n之间的所有奇数
	int start = 0, end;
	cin >> end;
	do{
		if(start % 2){
			cout << start << ' ';
		}
		start ++;
	}while(start <= end);
	
	return 0;
}
```
**4. for循环**
```c++
#include <iostream>

using namespace std;

int main(){
	// 输出0 ~ 100之间的所有偶数之和
	int sum = 0;
	
	for(int i=0; i<=100; i++){ // 0是初始值，小于等于100是条件，自增是对于i的操作
		if(!(i % 2)){
			sum += i;
		}
	}
	cout << sum << endl;

	// 双重for循环：输出乘法口诀表
	for(int i=1; i<=9; i++){
		for(int j=1; j<=i; j++){
			cout << i << 'x' << j << '=' << i * j << '\t';
		}
		cout << endl;
	}
	
	return 0;
}
```
# 005 文件的写入和读取
 [[返回目录]](https://github.com/SacredDreams/C-Notes/blob/main/README.md#目录)  

**1. 主函数内输入输出**  
文字说明：输出从0 ~ n中除了x和y的所有数字  
*test.in*
```
120 55 80	
```
```test.in```文件中依次输入的为n、x、y  
*main.cpp*
```c++
#include <iostream>
#include <cstdio> // 文件读取和写入

using namespace std;

int main(){
	int n, x, y;
	
	freopen("test.in", "r", stdin); // 打开文件，准备读取
	freopen("test.out", "w", stdout); // 打开文件，准备写入
	
	cin >> n >> x >> y;

	for(int i=0; i<=n; i++){
		if(i == x || i == y){ // 如果i等于x或i等于y时条件成立
			continue; // 结束此次，继续执行下次
		}
		cout << i << ' ';
	}
	
	fclose(stdin); // 关闭文件
	fclose(stdout); // 关闭文件
	
	return 0;
}
```
*test.out*
```
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 51 52 53 54 56 57 58 59 60 61 62 63 64 65 66 67 68 69 70 71 72 73 74 75 76 77 78 79 81 82 83 84 85 86 87 88 89 90 91 92 93 94 95 96 97 98 99 100 101 102 103 104 105 106 107 108 109 110 111 112 113 114 115 116 117 118 119 120
```
```test.out```为输出结果，和控制台输出相同  
**2. 创建全局输入输出流**  
文字说明：输入a和b，计算a*b的结果  
*test1.in*
```
10 30
```
*main1.cpp*
```c++
#include <iostream>
#include <cstdio>

using namespace std;

// 创建全局输入输出流对象
ifstream in("test1.in");
ofstream out("test1.out");

// 如果起名时为cin和cout需要屏蔽iostream中的cin和cout，如下：
// ifstream cin("test1.in");
// ofstream cout("test1.out");

int main(){
	int a, b;
	
	in >> a >> b;
	out << a * b << endl;
	
	// 屏蔽iostream中的cin和cout（对应上文注释代码部分）
	// std::ios::sync_with_stdio(false);
	// cin >> a >> b;
	// cout << a * b << endl;
	
	return 0;
}
```
*test1.out*
```
300
```
# 006 数组
 [[返回目录]](https://github.com/SacredDreams/C-Notes/blob/main/README.md#目录)  

















