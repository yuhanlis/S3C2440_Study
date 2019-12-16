### 注意
- SDRAM还未进行后续设置，根据Nand Flash启动过程，S3C2440的硬件会将Nand(SDRAM)中的前4K内容复制到片内RAM
- 当makefile中链接时，设置数据段`-Tdata `不能超过0x1000(即：4096=4K)；当超过4K时，一些全局变量可能读取不到，因此造成了printf的数字无法显示
- `-Tdata`为数据段，存放的为**一般的全局变量**