# SPDX-License-Identifier: GPL-2.0-only
#
# The touch drivers are described by Kbuild, which upstream only drives from
# bazel.  Give them the same wrapper the other techpacks in this tree use so
# they can be built with make -C $(KERNEL_SRC) M=$(M) as well.

KBUILD_OPTIONS += TOUCH_ROOT=$(KERNEL_SRC)/$(M)

all: modules

modules:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) modules $(KBUILD_OPTIONS)

modules_install:
	$(MAKE) INSTALL_MOD_STRIP=1 -C $(KERNEL_SRC) M=$(M) modules_install

%:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) $@ $(KBUILD_OPTIONS)

clean:
	rm -f *.o *.ko *.mod.c *.mod.o *~ .*.cmd Module.symvers
	rm -rf .tmp_versions
