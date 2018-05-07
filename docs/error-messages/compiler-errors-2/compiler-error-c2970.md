---
title: コンパイラ エラー C2970 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2970
dev_langs:
- C++
helpviewer_keywords:
- C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0775f9d771b2c9497b3dc731e26c6a3b4e6ab30c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2970"></a>コンパイラ エラー C2970
'class': テンプレート パラメーター 'param': 'arg': 非型引数として内部リンケージを持つオブジェクトを含む式を使用することはできません  
  
 テンプレート引数としては、名前または静的変数のアドレスを使うことはできません。 このテンプレート クラスでは、コンパイル時に評価される定数値が必要です。  
  
 次の例では、C2970 が生成されます。  
  
```  
// C2970.cpp  
// compile with: /c  
static int si;  
// could declare nonstatic to resolve all errors  
// int si;  
  
template <int i>   
class X {};  
  
template <int *pi>   
class Y {};  
  
X<si> anX;   // C2970 cannot use static variable in templates  
  
// this would also work  
const int i = 10;  
X<i> anX2;  
```