​                                             SF与OF关系判断两带符号数大小

SF:

1. SF = 0，OF = 0：表示 ![[公式]](https://www.zhihu.com/equation?tex=a-b%3E0) 并且结果没有溢出，所以很直观可以知道 ![[公式]](https://www.zhihu.com/equation?tex=a%3Eb) ;
2. SF = 1，OF = 1： ![[公式]](https://www.zhihu.com/equation?tex=a-b) 可以表示成 ![[公式]](https://www.zhihu.com/equation?tex=a%2B%5B-b%5D_%7B%E8%A1%A5%7D) ，而由OF = 1，可知结果溢出，那么也就表示 ![[公式]](https://www.zhihu.com/equation?tex=a) 与 ![[公式]](https://www.zhihu.com/equation?tex=%5B-b%5D_%7B%E8%A1%A5%7D) 同号，但是与结果异号，然而结果符号位为1，所以 ![[公式]](https://www.zhihu.com/equation?tex=a%2C%5B-b%5D_%7B%E8%A1%A5%7D) 的符号位为0，也就是说在SF = OF = 1的情况下， ![[公式]](https://www.zhihu.com/equation?tex=a) 必为正或0，而b必为负数或者0，当ZF = 0，的限定下，那么 ![[公式]](https://www.zhihu.com/equation?tex=a-b%3E0)也就是 ![[公式]](https://www.zhihu.com/equation?tex=a%3Eb) 必然成立。

## SF != OF的情况

和上面的分析一样，很容易能得出：当SF != OF时表示的是小于。

状态标志是16位[标志寄存器](https://baike.baidu.com/item/标志寄存器/5757541)PSW用来存放运算结果的特征，常用作后续条件转移指令的转移控制条件。其中7位没用，9位标志位分成两类：一类为状态标志，表示运算后结果的状态特征，它影响后面的操作。状态标志有CF PF AF ZF SF和OF等6个。另一类为控制标志，用来控制CPU操作，控制标志有TF IF和DF3个。 状态标志位记录了算术和逻辑运算的一些特征。如：结果是否为0，是否有进位，借位，结果是否溢出等。不同指令对标志位具有不同的影响。



CF(进位标志位)Carry Flag

当进行加（减）法运算时，若最高位向前有进（借）位，则CF=1，否则CF=0。

应当注意的是，减法的CF被规定为小数减大数(无符号数)就置为1，所以不应当考虑减法最终是否转化为补码加法的问题。



PF(奇偶标志位)Parity Flag

当运算结果中低8位的“1”的个数为[偶数](https://baike.baidu.com/item/偶数)时PF=1，为奇数时，PF=0。



AF(辅助进位)Assist Flag

在加（减）法操作中，bit3向bit4有进位（借位）发生时，AF=1，否则AF=0。DAA和DAS指令测试这个标志位，以便在BCD加法或减法之后调整AL中的值。

1字节为8bit 对应为 bit7|bit6|bit5|bit4 bit3|bit2|bit1|bit0 前四个为高4位，后四个为低4位

简单来说，AF就是用来判断 中间进位没有。即8位[二进制](https://baike.baidu.com/item/二进制/361457)操作数 第四位有无进位给第五位



ZF(零标志位) Zero Flag

当运算结果为零时ZF=1,否则ZF=0。



SF(符号标志位)Symbol Flag

当运算结果的最高位为1时SF=1，否则SF=0



OF(溢出标志位)Overflow Flag

当算术运算结果超出了带符号数的范围，即溢出时，OF=1，否则OF=0.

