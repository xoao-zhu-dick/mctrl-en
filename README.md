# mctrl-en
no copyright,only translate
# mctrl Mctrl usage tutorial 
>test text
>this only translate page,upload 3.14.2020 author link https://github.com/sadreminder/mctrl/blob/master/guide.md
> ~~ngt maybe write a useful code~~

## Catalog
> [1. what is mctrl ](#1-mctrl-是什么)  
> [2. mctrl code](#2-mctrl-指令)  
> [2.1 mctrl control](#21-mctrl-指令的使用方法)  
> [2.2 DataMap extend ](#22-datamap-扩展)

### 1.what is mctrl
Full name ModelCtrl，can control

### 2.mctrl code

`/mctrl <target> <category> <value>`  
Objectives：`@a` All，`@n` nearst，`@r:00` Scope or entity name (default `no_name`)

#### 2.1 mctrl way to use

- Instructions are risky and prudent.
- Be careful **Whether the wrong number is broken down**

category| control | Effect | when mistake yes or no eixt game
:-- | :-- | :-- | :--
`notch` | `mctrl <train> notch <-8 ~ 5>` | control speed gear | **yes**
`dir` | `mctrl <train> dir <0 or 1>` | train toward (`0` forward，`1` back) | **yes**
`dm:<data name>` | `mctrl <any> dm:<data name> <(type)value>` | eidt DataMap | no
`state:<data name>` | `mctrl <vehicle> state:<data name> <value>` | none | none
`move` | `mctrl <vehicle> move <distance>` | move vehicle | none
`addYaw` | `mctrl <vehicle or artillery> addYaw <value>` | Adjusting vehicle (yaw)| no
`addPitch` | `mctrl <artillery> addPitch <value>` | shuot down | no

For example：we want to set up a vehicle named `test`  The gear of the train is `3`，than `mctrl test notch 3` finish

#### 2.2 DataMap extension

1）every entity has DataMap data, and DataMap data can be adjusted to control components.

- DataMap data name should be consistent in case and case

2）↓ use control train 

- if eidt `Notch` and `Direction` can use `mctrl <train> <notch or dir> <value>` Replace

DataMap data name | en-lang | category | vlue | Remarks
:-- | :-- | :-- | :-- | :--
`Role` | train point | `Int` | `0` forward，`1` mid，`2` back | none
`Destination` | Destination | `Int` | first `0`，an than | none
`Announcement` | Announcement | `Int` | first `0`，an than | eidt json in game,can't play
`Light` | Light | `Int` | `0` off，`1` onpe forward，`2` onpe back | none
`Pantograph` | antograph | `Int` | `0` down，`1` up | none
`Notch` | gear | `Int` | `-8 ~ 5` | **when mistake yes or no eixt game**
`InteriorLight` | InteriorLight | `Int` | `0` off，`1` open，`2` colorful | none
`Direction` | towrad | `Int` | `0` forward，`1` back | seat (bug)，**when mistake yes or no eixt game**
`ChunkLoader` | Chunk | `Int` | `0 ~ 8` | none
`Door` | door | `Int` | `0` all close，`1` lift side，`2` right side，`3` all open | none

For example：we want to set up a vehicle named  `test2`  The train door is fully opened, then`mctrl test2 dm:Door (Int)3`finish

#### 2.3  the realization method of automatic driving.
**to be continued**
