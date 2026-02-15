# KernelSU and SUSFS Build Instructions

This document provides the necessary steps to build KernelSU and SUSFS for the android_kernel_motorola_sm8550 repository.

## Prerequisites

Before you begin, ensure that you have the following installed:

- A suitable Linux distribution (Ubuntu 20.04 or later is recommended)
- Required packages for building the kernel (`git`, `gcc`, `make`, etc.)
- A working environment for Android kernel development

## Clone the Repository

First, clone the kernel repository:

```bash
git clone https://github.com/JWEB0689/android_kernel_motorola_sm8550.git
cd android_kernel_motorola_sm8550
```

## Switch to the Appropriate Branch

Switch to the lineage-23.0 branch:

```bash
git checkout lineage-23.0
```

## Build Instructions

Follow these steps to build KernelSU and SUSFS:

1. **Set up the build environment**:
    ```bash
    source build/envsetup.sh
    lunch lineage_sm8550-userdebug
    ```

2. **Build the kernel**:
    ```bash
    make -j$(nproc)
    ```

3. **Flash the kernel (optional)** if you are ready to test:
    ```bash
    fastboot flash boot out/arch/arm64/boot/Image
    fastboot reboot
    ```

## Conclusion

You should now have a working KernelSU and SUSFS build. For additional information, refer to the official KernelSU and SUSFS documentation.