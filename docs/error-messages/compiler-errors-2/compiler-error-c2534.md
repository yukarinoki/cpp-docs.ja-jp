---
title: コンパイラ エラー C2534 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2534
dev_langs:
- C++
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bae52374e09852ffb68c5807353155d9928924eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228247"
---
# <a name="compiler-error-c2534"></a>コンパイラ エラー C2534
'identifier': コンス トラクターは値を返すことはできません  
  
 コンス トラクターの戻り値または戻り値の型であることはできません (であっても、`void`型を返す)。  
  
 このエラーは、削除することによって解決される可能性があります、`return`コンス トラクターの定義からのステートメント。  
  
 次の例では、C2534 が生成されます。  
  
```  
// C2534.cpp  
class A {  
public:  
   int i;  
   A() { return i; }   // C2534  
};  
```