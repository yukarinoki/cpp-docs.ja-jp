---
title: コンパイラの警告 (レベル 4) C4238 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4238
dev_langs:
- C++
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06dbec01da8d1b47cb7b93c90a22ae5266e9b4c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4238"></a>コンパイラの警告 (レベル 4) C4238
使用される標準の拡張機能: 左辺値として使用されるクラスの右辺値  
  
 Visual C、Microsoft 拡張機能の以前のバージョンとの互換性 (**/Ze**) を右辺値のコンテキストでその暗黙的または明示的には、アドレス、クラス型を使用できるようにします。 場合によっては、次の例などの危険な指定できます。  
  
## <a name="example"></a>例  
  
```  
// C4238.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
C * pC = &C();   // C4238  
```  
  
 この使用法、ANSI 互換のエラーが発生 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。