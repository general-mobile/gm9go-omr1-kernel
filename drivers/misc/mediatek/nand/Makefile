#
# Copyright (C) 2015 MediaTek Inc.
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License version 2 as
# published by the Free Software Foundation.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
# GNU General Public License for more details.
#

ifeq ($(CONFIG_MTK_COMBO_NAND_SUPPORT),y)
CONFIG_NANDX_MK_KERNEL := y
include $(srctree)/drivers/misc/mediatek/nand/nandx/Nandx.mk
else
ifeq ($(CONFIG_MTK_NAND_V2),y)
obj-y += v2/
else
obj-y += v1/
endif
endif
