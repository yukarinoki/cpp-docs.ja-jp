---
title: コンパイラの警告 (レベル 4) C4232 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4232
dev_langs:
- C++
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 093f9eeeb27b402b58f3d53ae34952c34dca3779
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4232"></a>コンパイラの警告 (レベル 4) C4232
使用される標準の拡張機能: 'identifier': dllimport 'dllimport' のアドレスは静的、身元は保証されません  
  
 Microsoft 拡張機能 (/Ze) で宣言された関数のアドレス、静的でない値を与えることができます、 **dllimport**修飾子です。 ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))、このエラーが発生します。  
  
 次の例では、C4232 が生成されます。  
  
```  
// C4232.c  
// compile with: /W4 /Ze /c  
int __declspec(dllimport) f();  
int (*pfunc)() = &f;   // C4232  
```