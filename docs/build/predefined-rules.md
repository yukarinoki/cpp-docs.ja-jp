---
title: 定義済み規則
ms.date: 11/04/2016
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
ms.openlocfilehash: b4b8ca7b0126ca42b2144aa094e7f766f6344b2a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609691"
---
# <a name="predefined-rules"></a>定義済み規則

組み込み推論規則では、NMAKE のコマンド マクロおよびオプション マクロが使用されます。

|ルール|コマンド|既定値<br /><br /> アクション|Batch<br /><br /> ルール|nmake が実行されるプラットフォーム|
|----------|-------------|------------------------|--------------------|----------------------------|
|.asm.exe|$(AS) $(AFLAGS) $<|ml $<|Ｘ|x86|
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml /c $<|可|x86|
|.asm.exe|$(AS) $(AFLAGS) $<|ml64 $<|Ｘ|X64|
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml64 /c $<|可|X64|
|.c.exe|$(CC) $(CFLAGS) $<|cl $<|no|all|
|.c.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|可|all|
|.cc.exe|$(CC) $(CFLAGS) $<|cl $<|no|all|
|.cc.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|可|all|
|.cpp.exe|$(CPP) $(CPPFLAGS) $<|cl $<|no|all|
|.cpp.obj|$(CPP) $(CPPFLAGS) /c $<|cl /c $<|可|all|
|.cxx.exe|$(CXX) $(CXXFLAGS) $<|cl $<|no|all|
|.cxx.obj|$(CXX) $(CXXFLAGS) /c $<|cl /c $<|可|all|
|.rc.res|$(RC) $(RFLAGS) /r $<|rc /r $<|Ｘ|all|

## <a name="see-also"></a>関連項目

[推論規則](../build/inference-rules.md)