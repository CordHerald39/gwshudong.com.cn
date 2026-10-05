---
title: "Steam 游戏换硬盘不想重下：迁移安装目录与本地存档检查"
description: "Steam 游戏换硬盘不想重下：迁移安装目录与本地存档检查。按适用条件、操作步骤、失败分支和官方参考逐项检查。"
date: "2026-10-06"
category: "tutorials"
updated: "2026-10-06"
author: "GW 树洞 内容编辑"
draft: false
label: "海外游戏主机数字服务"
---

换硬盘、腾系统盘，又不想把已装 Steam 游戏整包重下时，适用本文。处理方向是优先走客户端 Settings 里 Storage 的官方 Move：先在目标盘建库，再勾选游戏迁移安装目录。安装文件不等于全部存档，未进 Steam Cloud 的第三方进度多半不在 steamapps 里，应先备份再搬家。整包剪切 Steam 文件夹并删掉旧目录里大量文件属于高风险路径，不是首选。本文也不处理云存档与本地冲突、选错版本互相覆盖的问题。步骤与警告见 [Moving a Steam Installation and Games](https://help.steampowered.com/en/faqs/view/4BD4-4528-6B2E-8327)。

## 同一台电脑：先建库再用 Storage 的 Move

默认安装位置是 C:\Program Files (x86)\Steam\steamapps\common\。可以在任意驱动器另建路径，供以后安装选用。打开客户端 Settings 菜单，进入 Storage 选项卡，可查看当前默认安装盘，顶部用 “+” 新建路径。建好后，今后安装可以选到新位置；已装游戏不会因此自动搬家。

要在同一台电脑上把已装游戏换到别的位置、且不必先卸载：先按上面建好另一个 Steam Library 路径，再打开 Settings 的 Storage，选中游戏所在盘，勾选要搬的游戏，点 Move。这是官方针对“只搬家、不重下”的流程。未先建目标库就无法 Move。该功能针对同一台电脑上的不同位置，不能拿来直接把库“搬”到另一台机器。官方不建议把 Steam 装到移动硬盘，存在性能问题。

## 安装目录搬完，本地存档未必跟着走

Move 搬的是游戏安装文件夹，并不等于把所有进度一并带走。各游戏开发者自行决定存档方式和位置。未保存在 Steam Cloud 的第三方游戏进度，多数可在当前 Windows 用户 Documents 下的 My Games 找到，路径形如 C:\Users\用户名\Documents\My Games\。换硬盘时把该文件夹放到新盘对应用户目录，才能保住这类存档和配置。找不到时，需向该游戏的开发商或发行商确认位置，不要假定 steamapps 里已经包含全部进度。

这与云存档冲突是两件事：此处问的是文件是否还在新盘上，不是云和本地哪一份被采用。动手前应备份 steamapps，以及 Documents 里的 My Games 等第三方存档。整包迁移前，官方也强烈建议备份 steamapps；没有备份又中途失败，只能逐个重装游戏。可用 [Steam Backup Feature](https://help.steampowered.com/en/faqs/view/4593-5CB7-DC3C-64F0) 做游戏备份，换电脑时更应走备份而不是 Storage 的 Move。

## 整包搬家、失败分支和替代办法

只搬家、不改 Steam 本体时，用上一节的 Move 即可。若要把整个 Steam 安装连同游戏换到新位置，须先确认登录名、密码，以及帐户已绑定当前邮箱，以便必要时重置密码。官方简单做法是：退出客户端，进入安装目录（默认 C:\Program Files (x86)\Steam\），删掉除 steamapps、userdata 和 steam.exe 以外的文件和文件夹，再把整个 Steam 文件夹剪切到新位置（例如 D:\Games\Steam\），启动并登录。之后对已装游戏做 [完整性验证](https://help.steampowered.com/en/faqs/view/0C48-FCBD-DA71-93EB)。日后内容会下到新目录的 steamapps。该流程会删除旧目录中大量文件，出错且无备份就要重装，因此不要把它当成换硬盘的第一选择。

若搬家过程或在新位置启动出错，需更彻底的步骤：退出客户端，把新位置里的 steamapps 先挪到桌面；按 [卸载说明](https://help.steampowered.com/en/faqs/view/3C73-90F9-F600-0266) 卸载以清除旧的 Windows 注册表设置；再按 [安装说明](https://help.steampowered.com/en/faqs/view/099E-F5D1-8780-4778) 装到目标位置；把 steamapps 放回新安装目录，以带上已下载内容、设置以及可能存在其中的存档；启动并登录确认；再验证完整性。同时把 Documents 下 My Games 迁到新盘对应用户目录。不保证一次 Move 或整包剪切都能免下；失败时以备份和完整性验证为退路，不要在无备份时删掉旧 steamapps。
