---
description: '詳細情報: 定義済みの規則'
title: 定義済み規則
ms.date: 11/04/2016
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
ms.openlocfilehash: 302c649980050764d1bb2f0e9a43b785d0175a09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225831"
---
# <a name="predefined-rules"></a>定義済み規則

組み込み推論規則では、NMAKE のコマンド マクロおよびオプション マクロが使用されます。

|ルール|コマンド|Default<br /><br /> action|Batch<br /><br /> ルール|nmake が実行されるプラットフォーム|
|----------|-------------|------------------------|--------------------|----------------------------|
|.asm.exe|$ (AS) $ (AFLAGS) $<|ml $<|no|x86|
|.asm.obj|$ (AS) $ (AFLAGS)/c $<|ml/c $<|はい|x86|
|.asm.exe|$ (AS) $ (AFLAGS) $<|ml64.exe $<|no|X64|
|.asm.obj|$ (AS) $ (AFLAGS)/c $<|ml64.exe/c $<|はい|X64|
|.c.exe|$ (CC) $ (CFLAGS) $<|cl $<|no|all|
|.c.obj|$ (CC) $ (CFLAGS)/c $<|cl/c $<|はい|all|
|.cc.exe|$ (CC) $ (CFLAGS) $<|cl $<|no|all|
|.cc.obj|$ (CC) $ (CFLAGS)/c $<|cl/c $<|はい|all|
|.cpp.exe|$ (CPP) $ (CPPFLAGS) $<|cl $<|no|all|
|.cpp.obj|$ (CPP) $ (CPPFLAGS)/c $<|cl/c $<|はい|all|
|.cxx.exe|$ (.CXX) $ (CXXFLAGS) $<|cl $<|no|all|
|.cxx.obj|$ (.CXX) $ (CXXFLAGS)/c $<|cl/c $<|はい|all|
|.rc.res|$ (RC) $ (RFLAGS)/r $<|rc/r $<|no|all|

## <a name="see-also"></a>関連項目

[推論規則](inference-rules.md)
