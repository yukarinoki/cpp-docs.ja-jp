---
title: コンパイラ エラー C3519 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3519
dev_langs:
- C++
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 740fef32484164e7439335686adce0a4aa8027f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3519"></a>コンパイラ エラー C3519
'invalid_param': embedded_idl 属性に対して無効なパラメーター  
  
 渡されたパラメーター、`embedded_idl`の属性[#import](../../preprocessor/hash-import-directive-cpp.md)コンパイラでは、パラメーターは認識されませんでしたが、します。  
  
 許可されているパラメーターのみ`embedded_idl`は`emitidl`と`no_emitidl`です。  
  
 次の例では、C3519 が生成されます。  
  
```  
// C3519.cpp  
// compile with: /LD  
[module(name="MyLib2")];  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")     
// C3519  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")     
// OK  
```