# In case the platform does NOT support this type of sensors
ccflags-y += -I$(srctree)/drivers/misc/mediatek/sensors-1.0/hwmon/include
ccflags-y += -I$(srctree)/drivers/misc/mediatek/sensors-1.0/accelerometer/inc
ccflags-y += -I$(srctree)/drivers/misc/mediatek/sensors-1.0/magnetometer/inc
ccflags-y += -I$(srctree)/drivers/misc/mediatek/sensors-1.0/include

# Vanzo:yucheng on: Mon, 13 Mar 2017 16:37:39 +0800
# added for aosp management to import our variable
project_name:=$(shell echo $(VANZO_INNER_PROJECT_NAME))
ifneq ($(strip $(project_name)),)
-include $(srctree)/../zprojects/$(project_name)/$(project_name).mk
VANZO_PROJECT_HEADERS:=$(srctree)/../zprojects/$(project_name)/kernel-headers
ccflags-y += -I$(VANZO_PROJECT_HEADERS)
endif
# End of Vanzo: yucheng

obj-y   +=  mag.o
obj-y   +=  mag_factory.o

ifeq ($(CONFIG_MTK_MAGHUB),y)
obj-y   +=  maghub/
else
# Vanzo:yucheng on: Mon, 13 Mar 2017 16:38:03 +0800
project_name:=$(shell echo $(VANZO_INNER_PROJECT_NAME))
ifneq ($(project_name),)
custom_kernel_magnetometer:= $(addsuffix /, $(shell echo $(CUSTOM_KERNEL_MAGNETOMETER)))
$(info "custom_kernel_magnetometer:$(custom_kernel_magnetometer)")
ifneq ($(custom_kernel_magnetometer),)
obj-y += $(custom_kernel_magnetometer)
endif
else
# End of Vanzo: yucheng
obj-$(CONFIG_MTK_AKM09911)      +=  akm09911/
obj-$(CONFIG_MTK_ST480)         +=  st480/
obj-$(CONFIG_MTK_AKM09918)      +=  akm09918/
obj-$(CONFIG_MTK_MMC3680X)	+=  mmc3680x/
obj-$(CONFIG_MTK_MMC5603X)	+=  mmc5603x/
obj-$(CONFIG_MTK_QMCX983)	+=  qmcX983/
obj-$(CONFIG_MTK_AKM09911)      +=  akm09911/
obj-$(CONFIG_MTK_ST480)         +=  st480/
obj-$(CONFIG_MTK_AKM09918)      +=  akm09918/
obj-$(CONFIG_MTK_MMC3630X)      +=  mmc3630/
# Vanzo:yucheng on: Mon, 13 Mar 2017 16:38:32 +0800
# TODO: replace this line with your comment
# added for new structure config alsps
endif
# End of Vanzo: yucheng
endif
