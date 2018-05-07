---
title: コンパイラ エラー C2904 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2904
dev_langs:
- C++
helpviewer_keywords:
- C2904
ms.assetid: d5802f2e-d3fc-473d-aa04-36957b4eaca5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 003f907cd82abb5d3aa2ce8502074cc39d16699b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2904"></a>コンパイラ エラー C2904
'identifier': 名前は、現在のスコープで、テンプレートに対して使用されています。  
  
 重複する名前のコードを確認します。  
  
 次の例では C2904 が生成されます。  
  
```  
// C2904.cpp  
// compile with: /c  
void X();  // X is declared as a function  
template<class T> class X{};  // C2904  
```