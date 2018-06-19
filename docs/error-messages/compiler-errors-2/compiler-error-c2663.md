---
title: コンパイラ エラー C2663 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2663
dev_langs:
- C++
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f39f516b32aaf1159d47726d01623e253ee8b383
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235860"
---
# <a name="compiler-error-c2663"></a>コンパイラ エラー C2663
'function': 'this' ポインターの有効な変換がある番号のオーバー ロードがありません  
  
 コンパイラは変換できませんでした`this`メンバー関数のオーバー ロードされたバージョンのいずれかにします。  
  
 このエラーは、以外を呼び出すことによって発生することができます`const`メンバー関数を`const`オブジェクト。  考えられる解決策:  
  
1.  削除、`const`オブジェクトの宣言からです。  
  
2.  追加`const`メンバー関数のオーバー ロードのいずれかにします。  
  
 次の例では、C2663 が生成されます。  
  
```  
// C2663.cpp  
struct C {  
   void f() volatile {}  
   void f() {}  
};  
  
struct D {  
   void f() volatile;  
   void f() const {}  
};  
  
const C *pcc;  
const D *pcd;  
  
int main() {  
   pcc->f();    // C2663  
   pcd->f();    // OK  
}  
```