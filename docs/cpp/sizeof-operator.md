---
title: sizeof 演算子
ms.date: 11/04/2016
f1_keywords:
- sizeof_cpp
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
ms.openlocfilehash: 13e181bf84e359d433fbe951b1aa69320a1f0013
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186296"
---
# <a name="sizeof-operator"></a>sizeof 演算子

型のサイズに対して、オペランドのサイズを生成 **`char`** します。

> [!NOTE]
> 演算子の詳細については `sizeof ...` 、「[省略記号と可変個引数のテンプレート](../cpp/ellipses-and-variadic-templates.md)」を参照してください。

## <a name="syntax"></a>構文

```
sizeof unary-expression
sizeof  ( type-name )
```

## <a name="remarks"></a>解説

演算子の結果 **`sizeof`** は `size_t` 、インクルードファイルで定義されている整数型である型になり \<stddef.h> ます。 この演算子を使うと、コンピューターに依存するデータ サイズをプログラムで指定せずに済みます。

のオペランドには **`sizeof`** 、次のいずれかを指定できます。

- 型の名前。 型名と共にを使用するには、 **`sizeof`** 名前をかっこで囲む必要があります。

- 式。 式と共に使用する場合 **`sizeof`** は、かっこの有無にかかわらず、を指定できます。 式は評価されません。

演算子を **`sizeof`** 型のオブジェクトに適用すると **`char`** 、1が生成されます。 **`sizeof`** 演算子が配列に適用されると、配列のバイト数の合計が生成されます。配列の識別子によって表されるポインターのサイズではありません。 配列識別子によって表されるポインターのサイズを取得するには、を使用する関数にパラメーターとして渡し **`sizeof`** ます。 次に例を示します。

## <a name="example"></a>例

```cpp
#include <iostream>
using namespace std;

size_t getPtrSize( char *ptr )
{
   return sizeof( ptr );
}

int main()
{
   char szHello[] = "Hello, world!";

   cout  << "The size of a char is: "
         << sizeof( char )
         << "\nThe length of " << szHello << " is: "
         << sizeof szHello
         << "\nThe size of the pointer is "
         << getPtrSize( szHello ) << endl;
}
```

## <a name="sample-output"></a>サンプル出力

```Output
The size of a char is: 1
The length of Hello, world! is: 14
The size of the pointer is 4
```

**`sizeof`** 演算子が、、または型に適用されると、 **`class`** **`struct`** 結果は **`union`** その型のオブジェクトのバイト数に加え、ワード境界のメンバーを配置するために追加された埋め込みになります。 結果は、個々のメンバーのストレージ要件を追加することで計算されたサイズには必ずしも対応しません。 [/Zp](../build/reference/zp-struct-member-alignment.md)コンパイラオプションと[pack](../preprocessor/pack.md)プラグマは、メンバーのアラインメントの境界に影響します。

**`sizeof`** 空のクラスであっても、演算子は0を生成しません。

演算子は、 **`sizeof`** 次のオペランドと共に使用することはできません。

- 関数 (ただし、は **`sizeof`** 関数へのポインターに適用できます)。

- ビット フィールド。

- 定義されていないクラス。

- 型 **`void`** 。

- 動的に割り当てられる配列。

- 外部配列。

- 不完全な型。

- かっこで囲まれた不完全な型の名前。

**`sizeof`** 演算子が参照に適用されると、結果は、が **`sizeof`** オブジェクト自体に適用された場合と同じになります。

可変長配列が構造体の最後の要素である場合、 **`sizeof`** 演算子は配列のない構造体のサイズを返します。

演算子は、 **`sizeof`** 次の形式の式を使用して、配列内の要素の数を計算するためによく使用されます。

```cpp
sizeof array / sizeof array[0]
```

## <a name="see-also"></a>関連項目

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
