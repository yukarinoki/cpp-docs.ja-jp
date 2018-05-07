---
title: コンパイラ エラー C2758 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2758
dev_langs:
- C++
helpviewer_keywords:
- C2758
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34cce7840f888a4377440299a4dc5ac38ee6a1d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2758"></a>コンパイラ エラー C2758
'member': 参照型のメンバーは初期化する必要があります  
  
 初期化子リスト内の参照型のメンバーがコンストラクターによって初期化されていない場合、コンパイラ エラー C2758 が発生します。 コンパイラはそのメンバーを未定義のままにします。 参照型のメンバー変数は、コンストラクターの初期化リストで宣言されるか値を指定されるときに初期化する必要があります。  
  
 次の例では C2758 エラーが生成されます。  
  
```  
// C2758.cpp  
// Compile by using: cl /W3 /c C2758.cpp  
struct A {  
   const int i;  
  
   A(int n) { };   // C2758  
   // try the following line instead  
   // A(int n) : i{n} {};  
};  
```