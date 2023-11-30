gpio:  
![image](https://github.com/rosettarosettarosetta/rosetta-s-tech-stack/assets/110440346/7e750374-9932-4963-b956-ea1216e1a025)
左：模拟引脚  右：数字引脚

uart通讯  tx 发射  rx 接受端   22相对  （进缓冲区-发射-接受-暂存-读出） 
传输数据为通讯包  
由高低频表示数据         电线通常为高电平，变化时。。停止位
积偶校验


两边比特率要相同


蘋率看这一段时间的平均值
发送的是sscii：查表转换

void setup ()is init function 
void loop ()是循环


带～的引脚支持pwr

Arduino 文件的后缀名是.ino。  

同时，每一个 Ardino 程序都必须 setup 和 loop 这两个函数  
setup 函数中的代码仅会执行一次，而 loop 函数中的内容会不断地反复执行其中的代码。  

