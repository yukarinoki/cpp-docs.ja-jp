---
title: コンパイラ エラー C3919 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3919
dev_langs:
- C++
helpviewer_keywords:
- C3919
ms.assetid: 5f8eddda-d751-478b-930d-e18f7191ddfb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c210e85d9f53ae037852e880e12f3015c925642e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270991"
---
# <a name="compiler-error-c3919"></a>コンパイラ エラー C3919
'event_method': 関数は、型 'type' を持つ必要があります  
  
 イベントのアクセサー メソッドが正しく宣言されませんでした。  
  
 イベントの詳細については、次を参照してください。[イベント](../../windows/event-cpp-component-extensions.md)です。  
  
 次の例では、C3919 が生成されます。  
  
```  
// C3919.cpp  
// compile with: /clr /c  
using namespace System;  
delegate void D(String^);  
ref class R {  
   event D^ e {  
      int add(int);   // C3919  
      int remove(int);   // C3919  
  
      void add(D^);   // OK  
      void remove(D^);   // OK  
   }  
};  
```