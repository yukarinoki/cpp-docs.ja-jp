---
title: 定義済みの規則 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52c9440a0320bbc59e5d2552a53e13fae5e29f05
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572002"
---
# <a name="predefined-rules"></a>定義済み規則
組み込み推論規則では、NMAKE のコマンド マクロおよびオプション マクロが使用されます。  
  
|ルール|コマンド|既定値<br /><br /> アクション|Batch<br /><br /> ルール|nmake が実行されるプラットフォーム|  
|----------|-------------|------------------------|--------------------|----------------------------|  
|.asm.exe|$(AS) $(AFLAGS) $<|ml $<|Ｘ|x86|  
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml /c $<|可|x86|  
|.asm.exe|$(AS) $(AFLAGS) $<|ml64 $<|Ｘ|X64|  
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml64 /c $<|可|X64|  
|.c.exe|$(CC) $(CFLAGS) $<|cl $<|no|すべて|  
|.c.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|可|すべて|  
|.cc.exe|$(CC) $(CFLAGS) $<|cl $<|no|すべて|  
|.cc.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|可|すべて|  
|.cpp.exe|$(CPP) $(CPPFLAGS) $<|cl $<|no|すべて|  
|.cpp.obj|$(CPP) $(CPPFLAGS) /c $<|cl /c $<|可|すべて|  
|.cxx.exe|$(CXX) $(CXXFLAGS) $<|cl $<|no|すべて|  
|.cxx.obj|$(CXX) $(CXXFLAGS) /c $<|cl /c $<|可|すべて|  
|.rc.res|$(RC) $(RFLAGS) /r $<|rc /r $<|Ｘ|すべて|  
  
## <a name="see-also"></a>関連項目  
 [推論規則](../build/inference-rules.md)