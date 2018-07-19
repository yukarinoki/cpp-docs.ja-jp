---
title: コンパイラ エラー C2523 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2523
dev_langs:
- C++
helpviewer_keywords:
- C2523
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4546e576ced8d57a35c4c4861f29824a8d91d910
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228343"
---
# <a name="compiler-error-c2523"></a>コンパイラ エラー C2523
' クラス:: ~ identifier': デストラクターまたはファイナライザーのタグが一致しません  
  
 デストラクターの名前は、前にティルダ クラス名をする必要があります (`~`)。 コンス トラクターとデストラクターは、クラスと同じ名前を持つ唯一のメンバーです。  
  
 次の例では、C2523 が生成されます。  
  
```  
// C2523.cpp  
// compile with: /c  
class A {  
   ~B();    // C2523  
   ~A();   // OK  
};  
```