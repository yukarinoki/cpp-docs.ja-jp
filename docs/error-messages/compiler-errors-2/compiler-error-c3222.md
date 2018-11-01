---
title: コンパイラ エラー C3222
ms.date: 11/04/2016
f1_keywords:
- C3222
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
ms.openlocfilehash: 9f2c245e98609c8da8f5f89902d5c51bbf9d2b4f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638673"
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
