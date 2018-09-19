---
title: コンパイラ エラー C3222 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3222
dev_langs:
- C++
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30231f74b379cd9d69806fbd4b49ba0cb55ad871
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048319"
---
# <a name="compiler-error-c3222"></a>コンパイラ エラー C3222

'parameter': ジェネリック関数またはマネージドあるいは WinRT 型のメンバー関数に対して、既定引数を宣言できません

既定の引数を持つメソッド パラメーターを宣言することは許可されていません。 メソッドのオーバーロードは、この問題を回避する方法の 1 つです。 つまり、同じ名前でパラメーターを持たないメソッドを定義し、メソッド本体で変数を初期化します。

次の例では C3222 が生成されます。

```
// C3222_2.cpp
// compile with: /clr
public ref class G {
   void f( int n = 0 );   // C3222
};
```
