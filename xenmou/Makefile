obj-m := xenmou.o

KVERSION := $(shell uname -r)
KDIR := /lib/modules/$(KVERSION)/build
PWD := $(shell pwd)

default:
	$(MAKE) -C $(KDIR) M=$(PWD) modules -I$(PWD) EXTRA_CFLAGS="-g -I$(PWD)/include -I$(PWD)"

clean:
	$(MAKE) -C $(KDIR) M=$(PWD) clean

install:
	$(MAKE) -C $(KDIR) M=$(PWD) modules_install

load:
	-/sbin/rmmod xenmou
	/sbin/insmod xenmou.ko
