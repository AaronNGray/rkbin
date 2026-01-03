## Rockchip Loader Binaries Naming Rules

### General Rules:

Whether it is a single module or a merged loader, the naming convention is:

```
[chip]_[module]_[feature]_[version].[postfix]
```

**chip**:
Chip or chip-family name. Required.
Must be consistent with the names used in all kernel/U-Boot drivers.
The specific naming method is not discussed here.
Lowercase.

**module**:
Module name. Required.
Examples: `loader`, `ddr`, `miniloader`, `usbplug`, `bl3x`, `tee`, `tee_ta`.
Lowercase.

**feature**:
Module features. Optional. Multiple features are allowed.
Examples: DDR frequency used, support for a specific DDR type only, special options for miniloader, etc.
Lowercase.

**version**:
Version information. Required.
Format: `v1.00`.
Before official release: `0.xx`.
After official release: `1.00` or later.
Lowercase.

**postfix**:
File extension. Required.
Default output from compilation is `.bin`.
May also be `.elf`.
Merged images use `.img`.
Lowercase.

Underscore (`_`) is used as the separator.

**Example:**
File provided by the DDR module:

```
rk3228_ddr3_800MHz_v1.06.bin
```

---

### Special Rules:

#### 1. Naming of merged loaders:

* **loader**:
  A loader merged from `ddrbin`, `usbplug`, and `miniloader`, used by the Windows RK upgrade tool.

* **ubootloader**:
  A loader merged from `ddrbin`, `usbplug`, and U-Boot, used by the Windows RK upgrade tool.

* **idbloader**:
  A binary merged from `ddrbin` and a first-stage loader (miniloader or U-Boot) in IDB format, written directly to the IDB area.

**Note:**
The name *miniloader* only refers to the binary output of the miniloader project itself and is not used in the name of the merged loader.

---

#### 2. Version definition for merged loaders:

Format:

```
vx.yy.zzz
```

* **v**:
  Indicates “version”. This character is always used, lowercase.

* **x.yy**:
  Version number of the DDR file. Lowercase.

* **zzz**:

  * `[1]` Version number of the miniloader file, with the dot removed. Lowercase.
  * `[2]` Version number provided by U-Boot.

---

#### 3. Use uppercase letters where lowercase would cause ambiguity:

For example, `GB` in DDR should not be written as `gb`.

---

### Example:

Merged loader name:

```
rk3328_loader_v1.03.106.bin
```

Where:

* `1.03` is the DDR version number (`v1.03`)
* `106` is the miniloader version number (`v1.06`) with the dot removed

---
Rockchip loader binaries naming rule

总则：
不管单个模块，还是合并后的loader，命名都采用
[chip]_[module]_[feature]_[version].[postfix]

chip: 芯片或芯片系列名称, 必选项, 与所有kernel/uboot driver中的名称保持一致, 具体命名方式不在此讨论, 小写
module: 模块名称, 必选项, 如loader, ddr, miniloader，usbplug,bl3x,tee,tee_ta，小写
feature: 模块特征, 可选项, 可多个, 如ddr使用的频率, 或者只支持某个特定的ddr, miniloader的特别选项等, 小写
version: 版本信息, 必选项, 格式采用[v1.00,], 正式发布之前为0.xx, 正式发布后为1.00以后，小写
postfix: 后缀名, 必选项, 代码编译出来的默认为.bin, 也有可能为.elf, 合并后为.img，小写
连接符号采用下划线“_”
例如：
ddr模块提供的文件
rk3228_ddr3_800MHz_v1.06.bin

特殊规则：
1. 合并后的loader命名:
    loader: 由ddrbin, usbplug, miniloader合并而成可用于Windows RK升级工具使用的loader;
    ubootloader: 由ddrbin, usbplug, U-Boot合并而成可用于Windows RK升级工具使用的loader;
    idbloader: 由ddrbin, 一级loader(miniloader或uboot)按IDB格式合并直接用于烧写到IDB区的binary;
    注: miniloader的命名, 仅表示miniloader工程编译输出的bin, 不再延续到合并后的loader中使用;
2. 合并后的loader的version定义:
    vx.yy.zzz
v:  version的意思，一直采用这个字符，小写
x.yy: ddr所提供文件的版本号，小写
zzz: [1]是miniloader所提供文件的版本号，去掉点号的，小写
     [2]uboot提供的版本号

3. 命名小写会引起歧义的，就用大写
如ddr的GB，不能写成gb
举例：
合并好的loader命名：
rk3328_loader_v1.03.106.bin
其中的1.03是ddr的版本号v1.03
106是miniloader的版本号v1.06去掉点号的
