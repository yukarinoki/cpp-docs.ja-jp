---
title: sizeof 演算子
ms.date: 11/04/2016
f1_keywords:
- sizeof_cpp
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
ms.openlocfilehash: bc1165cf1df3933575013906d1b24673467f0b36
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178718"
---
# <a name="sizeof-operator"></a>sizeof 演算子

**Char**型のサイズに対して、オペランドのサイズを生成します。

> [!NOTE]
>  `sizeof ...` 演算子の詳細については、「[楕円と可変個引数のテンプレート](../cpp/ellipses-and-variadic-templates.md)」を参照してください。

## <a name="syntax"></a>構文

```
sizeof unary-expression
sizeof  ( type-name )
```

## <a name="remarks"></a>解説

**Sizeof**演算子の結果は `size_t`型になります。これは、インクルードファイル \<stddef.h > で定義されている整数型です。 この演算子を使うと、コンピューターに依存するデータ サイズをプログラムで指定せずに済みます。

**Sizeof**のオペランドは、次のいずれかになります。

- 型の名前。 型名と共に**sizeof**を使用するには、名前をかっこで囲む必要があります。

- 式。 式と共に使用する場合は、かっこの有無にかかわらず**sizeof**を指定できます。 式は評価されません。

型が**char**のオブジェクトに**sizeof**演算子を適用すると、1が生成されます。 **Sizeof**演算子が配列に適用されると、配列のバイト数の合計が生成されます。配列の識別子によって表されるポインターのサイズではありません。 配列識別子によって表されるポインターのサイズを取得するには、 **sizeof**を使用する関数にパラメーターとして渡します。 次に例を示します。

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

**Sizeof**演算子が**クラス**、**構造体型**、または**共用体型**に適用されている場合、結果はその型のオブジェクトのバイト数に加え、ワード境界のメンバーを配置するために追加された埋め込みになります。 結果は、個々のメンバーのストレージ要件を追加することで計算されたサイズには必ずしも対応しません。 [/Zp](../build/reference/zp-struct-member-alignment.md)コンパイラオプションと[pack](../preprocessor/pack.md)プラグマは、メンバーのアラインメントの境界に影響します。

**Sizeof**演算子は、空のクラスであっても0を生成しません。

**Sizeof**演算子は、次のオペランドと共に使用することはできません。

- 関数 (ただし、 **sizeof**は関数へのポインターに適用できます)。

- ビット フィールド。

- 定義されていないクラス。

- **Void**型。

- 動的に割り当てられる配列。

- 外部配列。

- 不完全な型。

- かっこで囲まれた不完全な型の名前。

**Sizeof**演算子が参照に適用されると、オブジェクト自体に**sizeof**が適用されている場合と同じ結果になります。

可変長配列が構造体の最後の要素である場合、 **sizeof**演算子は配列のない構造体のサイズを返します。

**Sizeof**演算子は、次の形式の式を使用して、配列内の要素の数を計算するためによく使用されます。

```cpp
sizeof array / sizeof array[0]
```

## <a name="see-also"></a>参照

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
