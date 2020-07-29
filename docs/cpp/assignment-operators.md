---
title: 代入演算子
description: C++ 標準言語代入演算子の構文とを使用します。
ms.date: 07/24/2020
f1_keywords:
- =
- '*='
- /=
- '%='
- +=
- -=
- <<=
- '>>='
- '&='
- ^=
- '|='
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], C++
- '&= operator'
- ^= operator
- += operator
- '>>= operator'
- '|= operator'
- operator>>=
- '*= operator'
- '%= operator'
- ^= operator
- operator >>=
- = operator
- -= operator
- /= operator
- <<= operator
ms.assetid: b028cf35-2ff1-4f14-9027-fd53ebec8aa0
ms.openlocfilehash: 91346d06c6fab4f3cd83c5318c88e738daf8d249
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229221"
---
# <a name="assignment-operators"></a>代入演算子

## <a name="syntax"></a>構文

*式**の代入-演算子の**式*

*assignment-operator*: 次のいずれか<br/>
&emsp;**`=`**&emsp;**`*=`**&emsp;**`/=`**&emsp;**`%=`**&emsp;**`+=`**&emsp;**`-=`**&emsp;**`<<=`**&emsp;**`>>=`**&emsp;**`&=`**&emsp;**`^=`**&emsp;**`|=`**

## <a name="remarks"></a>解説

代入演算子は、左側のオペランドで指定されたオブジェクトに値を格納します。 割り当て操作には、次の2種類があります。

- *単純な代入*。2番目のオペランドの値は、1番目のオペランドで指定されたオブジェクトに格納されます。

- *複合代入*。結果を格納する前に、算術演算、シフト演算、またはビットごとの演算が実行されます。

次の表に示す演算子を除くすべての代入演算子 **`=`** は、複合代入演算子です。

### <a name="assignment-operators-table"></a>代入演算子の表

| 演算子 | 意味 |
|--|--|
| **`=`** | 1 番目のオペランドで指定されたオブジェクトに、2 番目のオペランドの値を格納します (単純代入)。 |
| **`*=`** | 1 番目のオペランドの値に 2 番目のオペランドの値を乗算します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。 |
| **`/=`** | 1 番目のオペランドの値を 2 番目のオペランドの値で除算します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。 |
| **`%=`** | 2 番目のオペランドの値による 1 番目のオペランドの剰余を得ます。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。 |
| **`+=`** | 2 番目のオペランドの値を 1 番目のオペランドの値に加算します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。 |
| **`-=`** | 1 番目のオペランドの値から 2 番目のオペランドの値を減算します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。 |
| **`<<=`** | 1 番目のオペランドの値を 2 番目のオペランドの値で指定されたビット数の分だけ左にシフトします。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。 |
| **`>>=`** | 1 番目のオペランドの値を 2 番目のオペランドの値で指定されたビット数の分だけ右にシフトします。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。 |
| **`&=`** | 1 番目と 2 番目のオペランドのビットごとの AND を取得します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。 |
| **`^=`** | 1 番目と 2 番目のオペランドのビットごとの排他的 OR を取得します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。 |
| **`|=`** | 1 番目と 2 番目のオペランドのビットごとの包括的 OR を取得します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。 |

### <a name="operator-keywords"></a>演算子キーワード

複合代入演算子のうち3つは、キーワードに相当します。 これらは次のとおりです。

| 演算子 | 同等の |
|--|--|
| **`&=`** | **`and_eq`** |
| **`|=`** | **`or_eq`** |
| **`^=`** | **`xor_eq`** |

C++ では、これらの演算子キーワードを複合代入演算子の代替のスペルとして指定します。 C では、代替のスペルはマクロとしてヘッダーに記載されてい \<iso646.h> ます。 C++ では、代替のスペルはキーワードです。\<iso646.h>または C++ と同等のの使用 \<ciso646> は非推奨とされます。 Microsoft C++ では、 [`/permissive-`](../build/reference/permissive-standards-conformance.md) またはコンパイラオプションを使用して、 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 別のスペルチェックを有効にする必要があります。

## <a name="example"></a>例

```cpp
// expre_Assignment_Operators.cpp
// compile with: /EHsc
// Demonstrate assignment operators
#include <iostream>
using namespace std;
int main() {
   int a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555;

   a += b;      // a is 9
   b %= a;      // b is 6
   c >>= 1;      // c is 5
   d |= e;      // Bitwise--d is 0xFFFF

   cout  << "a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555" << endl
         << "a += b yields " << a << endl
         << "b %= a yields " << b << endl
         << "c >>= 1 yields " << c << endl
         << "d |= e yields " << hex << d << endl;
}
```

## <a name="simple-assignment"></a>単純代入

単純代入演算子 () を使用 **`=`** すると、2番目のオペランドの値が、1番目のオペランドで指定されたオブジェクトに格納されます。 両方のオブジェクトが数値型の場合、値を格納する前に、右オペランドが左側の型に変換されます。

**`const`** 型および型のオブジェクトは **`volatile`** 、だけの型の左辺値 **`volatile`** 、またはまたはではない型の左辺値に割り当てることができ **`const`** **`volatile`** ます。

クラス型 ( **`struct`** 、、および型) のオブジェクトへの代入 **`union`** は、 **`class`** という名前の関数によって実行され `operator=` ます。 この演算子関数の既定の動作は、ビットごとのコピーです。ただしこの動作は、オーバーロードした演算子により変更できます  詳細については、「[演算子のオーバーロード](../cpp/operator-overloading.md)」を参照してください。 クラス型には、*コピー代入*演算子と*移動代入*演算子を含めることもできます。 詳細については、「[コピーコンストラクターとコピー代入演算子](copy-constructors-and-copy-assignment-operators-cpp.md)」および「移動コンストラクター」および「[移動代入演算子](move-constructors-and-move-assignment-operators-cpp.md)」を参照してください。

特定の基底クラスからの任意の明確な派生クラスのオブジェクトは、その基底クラスのオブジェクトに代入できます。 派生クラスから基底クラスへの暗黙的な変換が行われていますが、基底クラスから派生クラスへの暗黙の変換は存在しないため、逆は当てはまりません。 次に例を示します。

```cpp
// expre_SimpleAssignment.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
class ABase
{
public:
    ABase() { cout << "constructing ABase\n"; }
};

class ADerived : public ABase
{
public:
    ADerived() { cout << "constructing ADerived\n"; }
};

int main()
{
    ABase aBase;
    ADerived aDerived;

    aBase = aDerived; // OK
    aDerived = aBase; // C2679
}
```

参照型への代入は、参照先のオブジェクトに対する代入であるかのように動作します。

クラス型オブジェクトでは、代入は初期化とは異なります。 代入と初期化がどのように異なるかを理解するために、次のコードを考えます

```cpp
UserType1 A;
UserType2 B = A;
```

前のコードは初期化子を示すもので、型 `UserType2` の引数をとる `UserType1` のコンストラクターを呼び出します。 次のコードでは

```cpp
UserType1 A;
UserType2 B;

B = A;
```

代入ステートメント

```cpp
B = A;
```

 には、次のいずれかの影響が考えられます。

- の関数を `operator=` 呼び出し `UserType2` `operator=` ます。引数を指定して指定し `UserType1` ます。

- 明示的な変換関数 `UserType1::operator UserType2` を呼び出します (そのような関数が存在する場合)。

- `UserType2::UserType2` 引数を取り、結果をコピーする `UserType1` コンストラクターを呼び出します (そのようなコンストラクターが存在する場合)。

## <a name="compound-assignment"></a>複合代入。

複合代入演算子は、[代入演算子の表](#assignment-operators-table)に示されています。 これらの演算子の形式は*e1* *op* =  *e2*です。ここで、 *e1*は変更できない左辺値で、 **`const`** *e2*は次のようになります。

- 算術型

- *op*がまたはの場合は、ポインターです。 **`+`****`-`**

E1 *e1* *op*の =  *e2*形式は*e1* **`=`** *e1* *op* *e2*として動作しますが、 *e1*は1回だけ評価されます。

列挙型への複合代入によってエラー メッセージが生成されます。 左オペランドがポインター型の場合、右オペランドはポインター型であるか、または0に評価される定数式である必要があります。 左オペランドが整数型の場合、右オペランドをポインター型にすることはできません。

## <a name="result-of-assignment-operators"></a>代入演算子の結果

代入演算子は、代入後に、左のオペランドで指定されているオブジェクトの値を返します。 結果の型は左側のオペランドの型です。 代入式の結果は常に左辺値です。 これらの演算子の結合規則は、右から左方向です。 左のオペランドは、変更可能な左辺値である必要があります。

ANSI C では、代入式の結果は左辺値ではありません。 つまり、C では、有効な C++ 式は `(a += b) += c` 許可されません。

## <a name="see-also"></a>関連項目

[二項演算子を含む式](../cpp/expressions-with-binary-operators.md)<br/>
[C++ の組み込み演算子、優先順位、および結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 代入演算子](../c-language/c-assignment-operators.md)
