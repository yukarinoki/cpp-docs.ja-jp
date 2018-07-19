---
title: コンパイラ エラー C3911 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3911
dev_langs:
- C++
helpviewer_keywords:
- C3911
ms.assetid: b786da59-0e99-479d-bc0d-551126e940f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfff502e5dc4a9628f11fbcd46129646ed720ea6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274012"
---
# <a name="compiler-error-c3911"></a>コンパイラ エラー C3911
'event_accessor_method': 関数は、型 'signature' を含んでいなければなりません  
  
 イベントのアクセサー メソッドが正しく宣言されませんでした。  
  
 詳細については、次を参照してください。[イベント](../../windows/event-cpp-component-extensions.md)です。  
  
 次の例では、C3911 が生成されます。  
  
```  
// C3911.cpp  
// compile with: /clr  
using namespace System;  
delegate void H(String^, int);  
  
ref class X {  
   event H^ E1 {  
      void add() {}   // C3911  
      // try the following line instead  
      // void add(H ^ h) {}  
  
      void remove(){}  
      // try the following line instead  
      // void remove(H ^ h) {}  
  
      void raise(){}  
      // try the following line instead  
      // void raise(String ^ s, int i) {}  
   };  
};  
```