---
title: コンパイラの警告 (レベル 1) C4288 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4288
dev_langs:
- C++
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2c51bdc201b364d76f1692db8ee14973c90923f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276631"
---
# <a name="compiler-warning-level-1-c4288"></a>コンパイラの警告 (レベル 1) C4288
使用される標準の拡張機能: 'var': for ループで宣言したループ コントロール変数が for ループのスコープです外部で使用。外側のスコープ内の宣言と競合します。  
  
 コンパイルするときに[/Ze](../../build/reference/za-ze-disable-language-extensions.md)と **/Zc:forscope-** で宣言された変数、**の**ループが後に使用された、[の](../../cpp/for-statement-cpp.md)-ループにスコープします。 C++ 言語に対する Microsoft 拡張機能により、この変数のスコープ内に存続して、C4288 は、変数の最初の宣言を使用しないことを通知します。  
  
 参照してください[/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)については、Microsoft の拡張機能を指定する方法について**の**/ze オプションでループします。  
  
 次の例では、C4288 が生成されます。  
  
```  
// C4288.cpp  
// compile with: /W1 /c /Zc:forScope-  
int main() {  
   int i = 0;    // not used in this program  
   for (int i = 0 ; ; ) ;  
   i++;   // C4288 using for-loop declaration of i  
}  
```