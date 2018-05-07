---
title: コンパイラ エラー C3468 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3468
dev_langs:
- C++
helpviewer_keywords:
- C3468
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a5d8b4fbdded1fc234e3f0de7e05c76d7164a16
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3468"></a>コンパイラ エラー C3468
'type': 型は次のアセンブリにのみ転送できます:  
  
 '`file`' はアセンブリではありません  
  
 アセンブリ内の型のみを転送することができます。  
  
 詳細については、次を参照してください。 [Type Forwarding (C + + CLI)](../../windows/type-forwarding-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 モジュールを作成する例を次に示します。  
  
```  
// C3468.cpp  
// compile with: /LN /clr  
public ref class R {};  
```  
  
## <a name="example"></a>例  
 次の例では C3468 が生成されます。  
  
```  
// C3468_b.cpp  
// compile with: /clr /c  
#using "C3468.netmodule"  
[ assembly:TypeForwardedTo(R::typeid) ];   // C3468  
```