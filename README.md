# Keil Setup Installation Guide for macOS

This guide walks you through installing Keil µVision on macOS using Wine, along with the necessary tools for the lab.



## Step 1: Install Homebrew (package manager for MacOS)

Homebrew is a package manager for macOS that simplifies software installation.

1. Open Terminal (Applications → Utilities → Terminal)

2. Install Homebrew by running:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

3. Follow the on-screen instructions and enter your password when prompted

4. After installation, verify Homebrew is installed:
```bash
brew --version
```

## Step 2: Install Wine for Mac (Kegworks or Sikarugir)


Install Wine via Homebrew:
```bash
brew install --cask Sikarugir-App/sikarugir/sikarugir
```


## Step 3: Install Keil µVision

1. Download the Keil C51 installer from [ARM's official website](https://www.keil.com/demo/eval/c51.htm)

2. Follow the instruction as shown in the video
 [keil installation](https://drive.google.com/file/d/1dCbQKq_vxq2rW5-cpNZmwz3437tNbkod/view?usp=sharing)


## Step 4: Install DFU Programmer

DFU (Device Firmware Update) Programmer is used for flashing firmware to microcontrollers.

1. Install via Homebrew:
```bash
brew install dfu-programmer
```

2. Verify installation:
```bash
dfu-programmer --version
```
3. Using DFU Programmer

Erase flash: Run the following command:

```bash
sudo dfu-programmer at89c5131 erase
```


Program flash: Run the following command:
```bash
sudo dfu-programmer at89c5131 flash <hex_file.hex>
```

Make sure you are in the directory where your hex file is present when you run this command.
Note: When typing your password with sudo, it won't be displayed on screen, but the system accepts it.

## Step 5: Install Prolific PL2303 Serial Driver

The PL2303 driver enables USB-to-serial communication.

### Install the Driver

1. Open appstore search for prolific PL2303 serial and install the below ones
   <img width="1292" height="836" alt="image" src="https://github.com/user-attachments/assets/e2e8a053-281c-4b67-9595-a0bbc3367d1f" />



### Install Serial Terminal (Cool term)

1. Open terminal and run the below commad for installtion of coolterm

```bash
brew install --cask coolterm
```
<img width="812" height="697" alt="image" src="https://github.com/user-attachments/assets/88817e97-f031-4201-9eaa-da378ac06c18" />




