# eXpOS (Experimental Operating System)

> Full documentation: [https://exposnitc.github.io/](https://exposnitc.github.io/)

## Prerequisites

- `gcc`, `flex`, `bison`, `make`, `wget`, `unzip`

## Build

```sh
make
```

This builds all components: `expl`, `spl`, `xfs-interface`, and `xsm`.

## Usage

### 1. Load the filesystem

Run `xfs-interface` to format the disk and load files:

```sh
cd xfs-interface
./xfs-interface
```

Inside the interface:
- `load --inode <file>` — load inode table
- `load --data <file>` — load data blocks
- `load --exec <file>` — load executable (XEXE format)
- `exit` — quit

### 2. Compile SPL programs

```sh
cd spl
./spl <file.spl>
```

Or use the batch script:

```sh
./compile_script.sh <stage> [file_name_without_extension]
```

### 3. Compile EXPL programs

```sh
cd expl
./expl <file.expl>
```

### 4. Run the simulator

```sh
cd xsm
./xsm <options>
```

Common flags:
- `--timer <ticks>` — enable timer interrupts at interval
- `--debug` — debug mode
- `--disk <disk_image>` — specify disk image

