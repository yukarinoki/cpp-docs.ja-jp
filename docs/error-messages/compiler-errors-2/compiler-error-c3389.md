---
title: コンパイラ エラー C3389 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3389
dev_langs:
- C++
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f0f60a1096c070d28be3b7af161bbb924fb20dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3389"></a>コンパイラ エラー C3389
/clr で __declspec(keyword) は使用できません:/clr:pure または/clr:safe  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で非推奨とされています。  
  
 A [_ _declspec](../../cpp/declspec.md)修飾子の使用を意味するプロセスの状態ごとです。  [/clr: 純粋な](../../build/reference/clr-common-language-runtime-compilation.md)意味、あたり[appdomain](../../cpp/appdomain.md)状態です。  そのために変数を宣言する、 `keyword` **_ _declspec**修飾子と指定してコンパイル **/clr: 純粋な**は許可されていません。  
  
 次の例では、C3389 が生成されます。  
  
```  
// C3389.cpp  
// compile with: /clr:pure /c  
__declspec(dllexport) int g2 = 0;   // C3389  
```