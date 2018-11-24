# 永远的7日之都(关于本次解密的详解)  
    注: 第一天猜人物是晏华，就不说了，主要针对后面的部分。  
___
## 第二天 条件
* 问题编码: \u0063\u0068\u0065\u0073\u0073\u0062\u006f\u0061\u0072\u0064\u002c\u0062\u0075\u006c\u006c\u0065\u0074\u002c\u0054\u0042\u0043\u002e
* 这是一段[ASCII](https://m.baidu.com/sf_bk/item/ASCII/309296?fr=aladdin&ms=1&rid=11039219159295600557)编码。
* 你可以通过一般的[在线编码转换](http://tool.oschina.net/encode?type=3)，由此得出这段编码转换为英文字符是chessboard,bullet,TBC.
* 不懂英语的话，用翻译软件得知，chessboard的中文意思是棋盘、bullet的中文意思是子弹。则根据这两个单词线索得出最终答案为: 神的棋盘
___
## 第三天  密钥
* 问题数组: 8 3 22 15 ( ) 35 50 ( ) 64 99 … 
* 这其实是一个等差数组。我们可以将这个数组分为两个部分。

|第一部分|8|22|( )|50|64|
|-------- | :--------: | :--------: |-------- | :--------: | :--------: |
|规律:相差14|8|8+14=22|22+14=(36)|36+14=50|50+14=64|

|第二部分|3|15|35|( )|99|
|-------- | :--------: | :--------: |-------- | :--------: | :--------: |
|规律:相差数每次加8|3|3+4+8=15|15+12+8=35|35+20+8=(63)|(63)+28+8=99|
* 最终答案: 8 3 22 15 (36) 35 50 (63) 64 99 … 
___
## 第四天 关键词一
* 问题数组: 65 18 5 55 57 74 23 224 180 234 223 204 185 169
* 总共有16个数字，我们获得到的提示为[XOR](https://baike.baidu.com/item/%E5%BC%82%E6%88%96/10993677?fr=aladdin)这是一种逻辑运算符，中文名叫异或(不懂的点击蓝色字体)。
* XOR异或实际上就是一种二进制数字的位与位的比较，相同为0，不同为1。
* 我们以数字10和11为例子，方便理解。  

|例|十进制|二进制|
|-------- | :--------: | :--------: |
| |10|1010|
| |11|1011|
|XOR|1|0001|
* 10 xor 11 = 1。把表格里10和11的二进制每一位进行比较，总共4位。1010 xor 1011。第一位1和1，相同为0。第二位0和0，相同为0。第三位1和1，相同为0。第四位0和1，不同为1。所以结果是二进制0001，转成10进制就是1啦。
* 根据线索，我们得知第三天的密钥其实就是关键。就是把第三天的那个等差数组XOR我们现在得到的数组。(根据实际的结果，我们得知需要取等差数组相差14的那组数据。也就是当中的偶数。)
* 已知今天有16个数据，所以昨天那组数据我们也要取16个相差14的数字进行XOR。
* 而XOR后的数据转回10进制并且对照ASCII获得最终的字符。
*详细表格如下:

|昨日等差14的数组|今日的数组|二进制XOR|十进制XOR|ASCII码|
|-------- | :--------: | :--------: |--------: |
|8|92|1000 XOR 01011100 = 01010100|8 XOR 92 = 84|t|
|22|126|00010110 XOR 01111110 = 01101000|22 XOR 126 = 104|h|




|36|65|
|50|18|
|64|5|
|78|55|
|92|57|
|106|74|
|120|23|
|134|224|
|148|180|
|162|234|
|176|223|
|190|204|
|204|185|
|218|169|
