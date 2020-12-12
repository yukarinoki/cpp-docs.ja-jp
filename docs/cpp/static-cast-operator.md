---
description: 詳細については、「static_cast 演算子」を参照してください。
title: static_cast 演算子
ms.date: 11/04/2016
f1_keywords:
- static_cast_cpp
helpviewer_keywords:
- static_cast keyword [C++]
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
ms.openlocfilehash: 7d76b4e21adea6561d7d6822871631c242aaf9c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317962"
---
# <a name="static_cast-operator"></a>static_cast 演算子

式に存在する型のみに基づいて、 *式* を *型 id* の型に変換します。

## <a name="syntax"></a>構文

```
static_cast <type-id> ( expression )
```

## <a name="remarks"></a>解説

標準 C++ では、変換の安全性を確認する実行時の型チェックはありません。 C++/CX では、コンパイル時チェックと実行時チェックが実行されます。 詳細については、「 [キャスト](casting.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

演算子は、 **`static_cast`** 基底クラスへのポインターを派生クラスへのポインターに変換するなどの操作に使用できます。 このような変換は、必ずしも安全であるとは限りません。

一般に、 **`static_cast`** 列挙型などの数値データ型を int や int に変換し、変換に関係するデータ型がある場合は、を使用します。 **`static_cast`** は **`dynamic_cast`** **`static_cast`** 実行時の型チェックが行われないため、変換は変換ほど安全ではありません **`dynamic_cast`** 。 が **`dynamic_cast`** あいまいなポインターに対して失敗すると、は **`static_cast`** 何も問題ないかのように戻ります。これは危険な場合があります。 **`dynamic_cast`** 変換は安全ですが、 **`dynamic_cast`** ポインターまたは参照に対してのみ機能し、実行時の型チェックはオーバーヘッドです。 詳細については、「 [Dynamic_cast 演算子](../cpp/dynamic-cast-operator.md)」を参照してください。

次の例では、`D* pd2 = static_cast<D*>(pb);` は `D` にないフィールドとメソッドがあるため、行 `B` は安全ではありません。 ただし、`B* pb2 = static_cast<B*>(pd);` には `D` のすべてが常に含まれているため、行 `B` は安全な変換です。

```cpp
// static_cast_Operator.cpp
// compile with: /LD
class B {};

class D : public B {};

void f(B* pb, D* pd) {
   D* pd2 = static_cast<D*>(pb);   // Not safe, D can have fields
                                   // and methods that are not in B.

   B* pb2 = static_cast<B*>(pd);   // Safe conversion, D always
                                   // contains all of B.
}
```

[Dynamic_cast](../cpp/dynamic-cast-operator.md)とは異なり、の変換に対して実行時チェックは行われません **`static_cast`** `pb` 。 `pb` によってポイントされるオブジェクトは、型 `D` のオブジェクトではない場合があります。その場合は、`*pd2` を使用すると、深刻な結果が発生する可能性があります。 たとえば、`D` クラスではなく、`B` クラスのメンバーである関数を呼び出すと、アクセス違反が発生する可能性があります。

**`dynamic_cast`** および演算子は、 **`static_cast`** クラス階層内でポインターを移動します。 ただし、は **`static_cast`** cast ステートメントで提供される情報にのみ依存しているため、安全でない可能性があります。 次に例を示します。

```cpp
// static_cast_Operator_2.cpp
// compile with: /LD /GR
class B {
public:
   virtual void Test(){}
};
class D : public B {};

void f(B* pb) {
   D* pd1 = dynamic_cast<D*>(pb);
   D* pd2 = static_cast<D*>(pb);
}
```

`pb` が `D` 型のオブジェクトを実際に指し示している場合、`pd1` および `pd2` は同じ値になります。 また、`pb == 0` の場合、同じ値も取得します。

が `pb` 型のオブジェクトを指し、 `B` 完全なクラスではない場合 `D` 、 **`dynamic_cast`** は0を返すのに十分なことを認識します。 ただし、は、 **`static_cast`** `pb` 型のオブジェクトを指すプログラマのアサーションに依存し、単純に `D` そのオブジェクトへのポインターを返し `D` ます。

したがって、は **`static_cast`** 暗黙的な変換の逆を行うことができ、その場合、結果は未定義になります。 プログラマは、変換の結果が安全であるかどうかを確認するために残されてい **`static_cast`** ます。

この動作は、クラス型以外の型にも適用されます。 たとえば、を使用して、 **`static_cast`** int からに変換でき **`char`** ます。 ただし、結果として得られるには、 **`char`** 値全体を保持するのに十分なビットがない可能性があり **`int`** ます。 ここでも、変換の結果が安全であるかどうかをプログラマが確認できるようになり **`static_cast`** ます。

また、演算子を使用して **`static_cast`** 、標準変換やユーザー定義変換など、暗黙的な変換を実行することもできます。 次に例を示します。

```cpp
// static_cast_Operator_3.cpp
// compile with: /LD /GR
typedef unsigned char BYTE;

void f() {
   char ch;
   int i = 65;
   float f = 2.5;
   double dbl;

   ch = static_cast<char>(i);   // int to char
   dbl = static_cast<double>(f);   // float to double
   i = static_cast<BYTE>(ch);
}
```

演算子は、 **`static_cast`** 整数値を列挙型に明示的に変換できます。 整数型の値が列挙値の範囲内にない場合、結果の列挙値は未定義になります。

演算子は、 **`static_cast`** null ポインター値を変換先の型の null ポインター値に変換します。

式は、演算子によって void 型に明示的に変換でき **`static_cast`** ます。 コピー先の void 型には **`const`** 、、、または属性をオプションで含めることができ **`volatile`** **`__unaligned`** ます。

**`static_cast`** 演算子は **`const`** 、、 **`volatile`** 、または属性をキャストできません **`__unaligned`** 。 これらの属性を削除する方法については、「 [Const_cast 演算子](../cpp/const-cast-operator.md) 」を参照してください。

**C++/CLI:** 再配置ガベージコレクターの上ではチェックされないキャストを実行する危険性があるため、を使用するのは、適切に動作することがわかっ **`static_cast`** ている場合にのみ、パフォーマンスクリティカルなコードにする必要があります。 をリリースモードで使用する必要がある場合は **`static_cast`** 、デバッグビルドの [safe_cast](../extensions/safe-cast-cpp-component-extensions.md) に置き換えて、成功したことを確認します。

## <a name="see-also"></a>関連項目

[キャスト演算子](../cpp/casting-operators.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
