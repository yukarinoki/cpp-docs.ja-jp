---
title: コンパイラエラー C2712
ms.date: 11/04/2016
f1_keywords:
- C2712
helpviewer_keywords:
- C2712
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
ms.openlocfilehash: a25c59fa5c9ba0102666f6c8922a61b063e7627a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202307"
---
# <a name="compiler-error-c2712"></a>コンパイラエラー C2712

> オブジェクト アンワインディングが必要な関数内で __try を使用できません。

## <a name="remarks"></a>解説

[/Ehsc](../../build/reference/eh-exception-handling-model.md)を使用すると、エラー C2712 が発生する可能性があります。また、構造化例外処理を伴う関数には、アンワインド (破棄) を必要とするオブジェクトも含まれています。

考えられる解決策:

- SEH を必要とするコードを別の関数に移動します。

- デストラクターを含むローカル変数とパラメーターを使用しないように、SEH を使用する関数を記述し直します。 コンストラクターまたはデストラクターで SEH を使用しないようにします。

- /EHsc を使用せずにコンパイルします。

[__Event](../../cpp/event.md)キーワードを使用して宣言されたメソッドを呼び出すと、エラー C2712 が発生することもあります。 イベントはマルチスレッド環境で使用される可能性があるため、コンパイラは、基になるイベントオブジェクトを操作できないようにするコードを生成し、生成されたコードを SEH [try-finally ステートメント](../../cpp/try-finally-statement.md)で囲みます。 その結果、イベント メソッドを呼び出し、型にデストラクターが含まれる引数を値渡しで渡すと、エラー C2712 が発生します。 このような場合の解決策の 1 つとして、引数を定数参照として渡します。

C2712 は、 **/clr: pure**を使用してコンパイルし、`__try` ブロック内のポインターから関数への静的配列を宣言した場合にも発生する可能性があります。 静的メンバーを使用するには、コンパイラが **/clr: pure**で動的な初期化C++を使用する必要があります。これは、例外処理を意味します。 しかし、`__try` ブロックでは C++ の例外処理を実行できません。

**/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

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
