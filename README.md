# ***efiSeek for Ghidra***

## About

The analyzer automates the process of researching EFI files, helps to discover and analyze well-known protocols, smi handlers, etc.

## Features

### Finds known EFI GUID's

![guids](./img/guids.png)

### Identifies protocols located with `LOCATE_PROTOCOL` function

![locateProtocols](./img/locateProtocols.png)

### Identifies functions used as the `NOTIFY` function

![notify](./img/notify.png)

### Identifies protocols installed in the module through `INSTALL_PROTOCOL_INTERFACE`

![install](./img/install.png)

### Identifies functions used as an interrupt function (like some hardware, software/child interrupt)

![ioTrap](./img/ioTrap.png)

![sx](./img/sx.png)

![child](./img/child.png)

![sw](./img/sw.png)

### Script for loading efi modules to relevant directories in `Headless mode`

Sorting smm modules relying on meta information into next folders:

* SwInterrupts
* ChildInterrupts
* HwInterrupts
* UnknownInterrupts

![sort](img/sort.png)

## Installation

### Windows

Set `GHIDRA_INSTALL_DIR` environment variable to ghidra path.

Start `gradlew.bat`, after the completion of building a copy archive from the `dist` directory to `GHIDRA_HOME_DIR/Extensions/Ghidra/`.
And turn on this extention in your ghidra.

### macOS

1. Set the `GHIDRA_INSTALL_DIR` environment variable:
```
export GHIDRA_INSTALL_DIR=/path/to/your/ghidra
```

2. Run the gradle wrapper to build the extension:
```
./gradlew
```

3. Copy the generated archive from the `dist` directory to your Ghidra extensions folder:
```
cp dist/*.zip $GHIDRA_INSTALL_DIR/Extensions/Ghidra/
```

4. Open Ghidra and enable the extension in the Project Manager under "File → Install Extensions..."

## Usage

After installation you are free to use this analyzer. If you open a EFI file, the analyzer appears selected automatically.
To start the analyzer, press `A` or `Analysis/Auto Analyze` and press `Analyze`.

## References

* https://github.com/al3xtjames/ghidra-firmware-utils
* https://github.com/danse-macabre/ida-efitools/