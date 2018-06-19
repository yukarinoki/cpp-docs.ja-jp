---
title: コンパイラ エラー C2427 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2427
dev_langs:
- C++
helpviewer_keywords:
- C2427
ms.assetid: a7d421af-6180-40b4-b7a6-9f3bc7dfaaf9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b98f04dd02b4881f3177afd93b2acf74a304b7fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196910"
---
# <a name="compiler-error-c2427"></a>コンパイラ エラー C2427
'class': このスコープでクラスを定義することはできません  
  
 入れ子になったクラスを定義しようとしましたが、入れ子になったクラスは、最も外側のクラスではなく、基底クラスのメンバー。  
  
 次の例では、C2427 が生成されます。  
  
```  
// C2427.cpp  
// compile with: /c  
template <class T>   
struct S {  
   struct Inner;   
};   
  
struct Y : S<int> {};   
  
struct Y::Inner {};   // C2427  
  
// OK  
template<typename T>  
struct S<T>::Inner {};  
```