## CNN的两种padding方式“SAME”和“VALID”

SAME：如果到边缘的时候剩下的范围不够卷积核大小了，往外 padding ，如果 padding 的是偶数，那么多的应该 padding 在右边（下边）
VALID：如果不够就直接舍去

