---
title: コンパイラ エラー C2726 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2726
dev_langs:
- C++
helpviewer_keywords:
- C2726
ms.assetid: f0191bb7-c175-450b-bf09-a3213db96d09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aaeab263c2deffe79de98be30808e2dca973ce56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236106"
---
# <a name="compiler-error-c2726"></a>コンパイラ エラー C2726
'gcnew' は、マネージ型または WinRT 型のオブジェクトの作成にのみ使用できます  
  
 ガベージ コレクション ヒープ上でネイティブ型のインスタンスを作成することはできません。  
  
 次の例では、C2726 を生成し、その修正方法を示しています。  
  
```  
// C2726.cpp  
// compile with: /clr  
using namespace System;  
class U {};  
ref class V {};  
value class W {};  
  
int main() {  
   U* pU = gcnew U;    // C2726  
   U* pU2 = new U;   // OK  
   V^ p2 = gcnew V;   // OK  
   W p3;   // OK  
  
}  
```  
