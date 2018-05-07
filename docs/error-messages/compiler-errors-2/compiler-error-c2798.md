---
title: コンパイラ エラー C2798 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2798
dev_langs:
- C++
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de30a19a2a27cde991cfce0ca061ce6f5447f033
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2798"></a>コンパイラ エラー C2798
'super::member' があいまいです。  
  
 複数の継承された構造体に含めるで参照されるメンバー [super](../../cpp/super.md)です。 いずれかでエラーを修正する可能性があります。  
  
-   D. の継承リストから B1 または B2 の削除  
  
-   B1 または B2 内のデータ メンバーの名前を変更します。  
  
 次の例では、C2798 が生成されます。  
  
```  
// C2798.cpp  
struct B1 {  
   int i;  
};  
  
struct B2 {  
   int i;  
};  
  
struct D : B1, B2 {  
   void g() {  
      __super::i = 4; // C2798  
   }  
};  
```