---
title: コンパイラエラー C2712
description: Microsoft C/c + + コンパイラエラー C2712 について説明します。
ms.date: 08/25/2020
f1_keywords:
- C2712
helpviewer_keywords:
- C2712
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
ms.openlocfilehash: 2f0b883607241473a429919e06de9e975fa2e3c1
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898692"
---
# <a name="compiler-error-c2712"></a>コンパイラエラー C2712

> `__try`オブジェクトのアンワインドを必要とする関数では使用できません

## <a name="remarks"></a>注釈

を使用すると、エラー C2712 が発生する可能性があり [`/EHsc`](../../build/reference/eh-exception-handling-model.md) ます。また、構造化例外処理を含む関数にも、アンワインド (破棄) を必要とするオブジェクトが含まれています。

考えられる解答:

- SEH を必要とするコードを別の関数に移動します。

- デストラクターを含むローカル変数とパラメーターを使用しないように、SEH を使用する関数を記述し直します。 コンストラクターまたはデストラクターで SEH を使用しないようにします。

- /EHsc を使用せずにコンパイルします。

キーワードを使用して宣言されたメソッドを呼び出すと、エラー C2712 が発生することもあり [`__event`](../../cpp/event.md) ます。 イベントはマルチスレッド環境で使用される可能性があるため、コンパイラは、基になるイベントオブジェクトの操作を防止し、生成されたコードを SEH [ `try-finally` ステートメント](../../cpp/try-finally-statement.md)で囲むコードを生成します。 その結果、イベント メソッドを呼び出し、型にデストラクターが含まれる引数を値渡しで渡すと、エラー C2712 が発生します。 このような場合の解決策の 1 つとして、引数を定数参照として渡します。

C2712 は、を使用してコンパイルし、 **`/clr:pure`** ブロック内のポインターから関数への静的配列を宣言した場合にも発生する可能性があり **`__try`** ます。 静的メンバーを使用するには、コンパイラがで動的な初期化を使用する必要があり **`/clr:pure`** ます。これは、C++ 例外処理を意味します。 ただし、C++ 例外処理はブロックでは許可されません **`__try`** 。

**`/clr:pure`** および **`/clr:safe`** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

## <a name="example"></a>例

次の例では、C2712 を生成し、その修正方法を示しています。

```cpp
// C2712.cpp
// compile with: /clr:pure /c
struct S1 {
   static int smf();
   void fnc();
};

void S1::fnc() {
   __try {
      static int (*array_1[])() = {smf,};   // C2712

      // OK
      static int (*array_2[2])();
      array_2[0] = smf;
    }
    __except(0) {}
}
```
