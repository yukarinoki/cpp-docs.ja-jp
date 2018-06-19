---
title: コンパイラ エラー C2790 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2790
dev_langs:
- C++
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11f1c90fed93666fad7513e2b4186a5baa2aa406
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232818"
---
# <a name="compiler-error-c2790"></a>コンパイラ エラー C2790
'super': このキーワードはクラス メンバー関数の本体内でのみ使用できます  
  
 ユーザーがこれまでしようとする場合は、キーワードを使用してこのエラー メッセージが表示される[super](../../cpp/super.md)メンバー関数のコンテキスト外でします。  
  
 次の例では、C2790 が生成されます。  
  
```  
// C2790.cpp  
void f() {  
   __super::g();   // C2790  
}  
```