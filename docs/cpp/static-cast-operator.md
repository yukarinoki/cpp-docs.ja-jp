---
title: static_cast 演算子
ms.date: 11/04/2016
f1_keywords:
- static_cast_cpp
helpviewer_keywords:
- static_cast keyword [C++]
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
ms.openlocfilehash: 37708bf50b28eb120af8e8a79e770c3121e6f509
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178588"
---
# <a name="static_cast-operator"></a>static_cast 演算子

式に存在する型のみに基づいて、*式*を*型 id*の型に変換します。

## <a name="syntax"></a>構文

```
static_cast <type-id> ( expression )
```

## <a name="remarks"></a>解説

標準 C++ では、変換の安全性を確認する実行時の型チェックはありません。 C++/CX では、コンパイル時チェックと実行時チェックが実行されます。 詳細については、「 [キャスト](casting.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

**Static_cast**演算子は、基底クラスへのポインターを派生クラスへのポインターに変換するなどの操作に使用できます。 このような変換は、必ずしも安全であるとは限りません。

一般に、列挙型などの数値データ型を int や int に変換し、変換に関係するデータ型を特定する場合は、 **static_cast**を使用します。 **static_cast**の変換は**dynamic_cast**変換ほど安全ではありません。 **static_cast**では実行時の型チェックが行われず、 **dynamic_cast**は実行されるためです。 あいまいなポインターへの**dynamic_cast**は失敗しますが、 **static_cast**は何も間違っていないかのように戻ります。これは危険な場合があります。 **Dynamic_cast**の変換は安全ですが、 **dynamic_cast**はポインターまたは参照に対してのみ機能し、実行時の型チェックはオーバーヘッドになります。 詳細については、「 [Dynamic_cast 演算子](../cpp/dynamic-cast-operator.md)」を参照してください。

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

[Dynamic_cast](../cpp/dynamic-cast-operator.md)とは異なり、`pb`の**static_cast**変換に対して実行時チェックは行われません。 `pb` によってポイントされるオブジェクトは、型 `D` のオブジェクトではない場合があります。その場合は、`*pd2` を使用すると、深刻な結果が発生する可能性があります。 たとえば、`D` クラスではなく、`B` クラスのメンバーである関数を呼び出すと、アクセス違反が発生する可能性があります。

**Dynamic_cast**演算子と**static_cast**演算子は、クラス階層内でポインターを移動します。 ただし、 **static_cast**は cast ステートメントで提供される情報にのみ依存しているため、安全でない可能性があります。 次に例を示します。

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

`pb` が `B` 型のオブジェクトを指し、完全な `D` クラスではない場合、 **dynamic_cast**は0を返すのに十分なことを認識します。 ただし、 **static_cast**は `D` 型のオブジェクトを指し `pb` プログラマのアサーションに依存しており、単に `D` オブジェクトへのポインターを返します。

その結果、暗黙的な変換の逆の処理を**static_cast**できます。その場合、結果は未定義になります。 プログラマは、 **static_cast**変換の結果が安全かどうかを検証することになります。

この動作は、クラス型以外の型にも適用されます。 たとえば、int から**char**への変換には**static_cast**を使用できます。 ただし、結果として得られる**char**には、 **int**値全体を保持するのに十分なビットがない可能性があります。 ここでも、 **static_cast**変換の結果が安全かどうかをプログラマが確認することになります。

**Static_cast**演算子を使用すると、標準変換やユーザー定義の変換など、暗黙的な変換を実行することもできます。 次に例を示します。

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

**Static_cast**演算子を使用すると、整数値を列挙型に明示的に変換できます。 整数型の値が列挙値の範囲内にない場合、結果の列挙値は未定義になります。

**Static_cast**演算子は、null ポインター値を変換先の型の null ポインター値に変換します。

**Static_cast**演算子により、任意の式を明示的に void 型に変換できます。 コピー先の void 型には、必要に応じて、 **const**、 **volatile**、または **__unaligned**属性を含めることができます。

**Static_cast**演算子は、 **const**、 **volatile**、 **__unaligned**の各属性をキャストできません。 これらの属性を削除する方法については、「 [Const_cast 演算子](../cpp/const-cast-operator.md)」を参照してください。

**C++/Cli:** 再配置ガベージコレクターの上ではチェックされないキャストを実行する危険性があるため、 **static_cast**を使用するのは、適切に動作することがわかっている場合にのみ、パフォーマンスクリティカルなコードにする必要があります。 リリースモードで**static_cast**を使用する必要がある場合は、デバッグビルドの[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)に置き換えて、成功したことを確認します。

## <a name="see-also"></a>参照

[キャスト演算子](../cpp/casting-operators.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
