################################################################################
# 自动生成的文件。不要编辑！
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include rt-thread/src/subdir.mk
-include rt-thread/libcpu/arm/cortex-m4/subdir.mk
-include rt-thread/libcpu/arm/common/subdir.mk
-include rt-thread/components/libc/compilers/gcc/newlib/subdir.mk
-include rt-thread/components/libc/compilers/common/subdir.mk
-include rt-thread/components/finsh/subdir.mk
-include rt-thread/components/drivers/src/subdir.mk
-include rt-thread/components/drivers/spi/subdir.mk
-include rt-thread/components/drivers/serial/subdir.mk
-include rt-thread/components/drivers/misc/subdir.mk
-include board/msp/subdir.mk
-include board/subdir.mk
-include applications/spi/subdir.mk
-include applications/led/subdir.mk
-include applications/lcd/subdir.mk
-include applications/subdir.mk
-include Libraries/rt_drivers/subdir.mk
-include Libraries/N32_Std_Driver/n32g45x_std_periph_driver/src/subdir.mk
-include Libraries/N32_Std_Driver/CMSIS/device/startup/subdir.mk
-include Libraries/N32_Std_Driver/CMSIS/device/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
SECONDARY_FLASH += \
rtthread.bin \

SECONDARY_SIZE += \
rtthread.siz \


# 所有目标
all: rtthread.elf secondary-outputs

# 工具调用
rtthread.elf: $(OBJS) $(USER_OBJS)
	arm-none-eabi-gcc -T "E:\2_Software_Project\Nation\demo\N32G45\board\linker_scripts\link.lds" -Xlinker --gc-sections -Wl,-Map,"rtthread.map" -Xlinker --cref -mcpu=cortex-m4 -mthumb -mfpu=fpv4-sp-d16 -mfloat-abi=hard -ffunction-sections -fdata-sections -Wl,--gc-sections,-Map=rt-thread.map,-cref,-u,Reset_Handler -o "rtthread.elf" $(OBJS) $(USER_OBJS) $(LIBS)

rtthread.bin: rtthread.elf
	arm-none-eabi-objcopy -O binary "rtthread.elf"  "rtthread.bin"

rtthread.siz: rtthread.elf
	arm-none-eabi-size --format=berkeley "rtthread.elf"

# 其他目标
clean:
	-$(RM) $(OBJS)$(SECONDARY_FLASH)$(SECONDARY_SIZE)$(ASM_DEPS)$(S_DEPS)$(S_UPPER_DEPS)$(C_DEPS) rtthread.elf
	-@echo ' '

secondary-outputs: $(SECONDARY_FLASH) $(SECONDARY_SIZE)

.PHONY: all clean dependents

-include ../makefile.targets
