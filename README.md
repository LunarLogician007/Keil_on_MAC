# macOS Setup Guide: Keil µVision & Lab Tools

This guide outlines the installation process for Keil µVision on macOS using the Wine compatibility layer, along with necessary drivers and flashing tools for the EE337 lab experiments.

---

## 1. Install Homebrew

Homebrew is a package manager for macOS required to install the necessary tools.

1. Open **Terminal** (`Applications` → `Utilities` → `Terminal`).
2. Run the following command to install Homebrew:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

```


3. Follow the on-screen prompts and enter your password when requested.
4. Verify the installation:
```bash
brew --version

```



---

## 2. Install Wine (Sikarugir)

Since Keil is a Windows application, we use a Wine wrapper to run it on macOS.

Run the following command in Terminal:

```bash
brew install --cask Sikarugir-App/sikarugir/sikarugir

```

---

## 3. Install Keil µVision (C51)

1. **Download:** Get the **C51** installer from [ARM's official website](https://www.keil.com/demo/eval/c51.htm).
2. **Install:** Follow the setup instructions demonstrated in the video guide below.
* [🎥 Watch Installation Guide](https://drive.google.com/file/d/1dCbQKq_vxq2rW5-cpNZmwz3437tNbkod/view?usp=sharing)



---

## 4. DFU Programmer

The **DFU (Device Firmware Update) Programmer** is used to flash `.hex` files onto the 8051 microcontroller.

### Installation

Install the tool via Homebrew:

```bash
brew install dfu-programmer

```

Verify the installation:

```bash
dfu-programmer --version

```

### Usage Guide


**1. Erase Flash**
Before programming, clear the existing firmware:

```bash
sudo dfu-programmer at89c5131 erase

```

**2. Program Flash**
Upload your new code:

```bash
sudo dfu-programmer at89c5131 flash <your_file.hex>

```
> **Note:** Execute these commands in the directory containing your `.hex` file. When using `sudo`, your password will not appear on screen as you type.
---

## 5. Serial Communication Setup

To enable UART communication between the microcontroller and your Mac, you must install the Prolific driver and a serial terminal.

### A. Install Prolific PL2303 Driver

1. Open the **App Store**.
2. Search for **"Prolific PL2303 Serial"**.
3. Install the application shown below:

<img width="800" alt="Prolific Driver App Store" src="(https://github.com/user-attachments/assets/e2e8a053-281c-4b67-9595-a0bbc3367d1f)" />

### B. Install CoolTerm

CoolTerm is the serial terminal used to view UART output.

1. Install via Homebrew:
```bash
brew install --cask coolterm

```


2. Once installed, open the application to verify.

<img width="600" alt="CoolTerm Interface" src="(https://github.com/user-attachments/assets/88817e97-f031-4201-9eaa-da378ac06c18)" />

---

