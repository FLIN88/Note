## CNN的两种padding方式“SAME”和“VALID”

SAME：如果到边缘的时候剩下的范围不够卷积核大小了，往外 padding ，如果 padding 的是偶数，那么多的应该 padding 在右边（下边）
VALID：如果不够就直接舍去

设图长为 $W$ ，填充后图长为 $W'$ ， 输出图长为 $W_{out}$ ，核长为 $F$ ，步长为 $S$ ，填充数量的 $P$ 推导如下：

SAME 的定义为 $W_{out} = \lceil \frac{W}{S} \rceil$

$W_{out} = \frac{W' - F}{2} + 1$ —— 填充后一定能整除，不需要取整

可得 $W' = (W_{out} - 1)S + F = SW_{out} + F - S$

因而 $P = W' - W = SW_out - W + F - S = S\lceil \frac{W}{S} \rceil - W + F - S$

当步长为 $1$ 时可简化为 $F - S$