
# 默认动作

default :
	../z_tools/make.exe img

# 镜像文件生成
# ipl.1st是中间文件.
ipl.bin : ipl.nas Makefile
	../z_tools/nask.exe ipl.nas ipl.bin ipl.lst

helloos.img : ipl.bin Makefile
	../z_tools/edimg.exe   imgin:../z_tools/fdimg0at.tek \
		wbinimg src:ipl.bin len:512 from:0 to:0   imgout:helloos.img

# 其他指令

asm :
	make -r ipl.bin

img :
	make -r helloos.img

run :
	make img
	copy helloos.img ..\z_tools\qemu\fdimage0.bin
	make -C ../z_tools/qemu

install :
	make img
	../z_tools/imgtol.com w a: helloos.img

clean :
	-del ipl.bin
	-del ipl.lst

src_only :
	make clean
	-del helloos.img