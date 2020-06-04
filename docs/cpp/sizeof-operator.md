---
title: sizeof 演算子
ms.date: 11/04/2016
f1_keywords:
- sizeof_cpp
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
ms.openlocfilehash: c9ae581b1b3bea522f2c1557b8be44ee1f32eef1
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032292"
---
# <a name="sizeof-operator"></a>sizeof 演算子

char**型の**サイズに対するオペランドのサイズを生成します。

> [!NOTE]
> 演算子の`sizeof ...`詳細については、「[省略記号と可変テンプレート](../cpp/ellipses-and-variadic-templates.md)」を参照してください。

## <a name="syntax"></a>構文

```
sizeof unary-expression
sizeof  ( type-name )
```

## <a name="remarks"></a>解説

**sizeof**演算子の結果は、インクルード`size_t`ファイル\<stddef.h>で定義された整数型の型です。 この演算子を使うと、コンピューターに依存するデータ サイズをプログラムで指定せずに済みます。

**sizeof**のオペランドは、次のいずれかになります。

- 型の名前。 **sizeof**を型名と共に使用するには、名前を括弧で囲む必要があります。

- 式。 式と共に使用する場合 **、sizeof**は括弧の有無にかかわらず指定できます。 式は評価されません。

**sizeof**演算子が**char**型のオブジェクトに適用されると、1 が返されます。 **sizeof**演算子を配列に適用すると、配列識別子で表されるポインターのサイズではなく、その配列の合計バイト数が返されます。 配列識別子で表されるポインタのサイズを取得するには、 **sizeof**を使用する関数にパラメータとして渡します。 次に例を示します。

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

**sizeof**演算子が**クラス** **、struct**、または**共用体**型に適用されると、その結果はその型のオブジェクトのバイト数に加えて、単語境界のメンバーを整列するために追加されたパディングになります。 結果は、個々のメンバーのストレージ要件を追加することで計算されたサイズには必ずしも対応しません。 [/Zp](../build/reference/zp-struct-member-alignment.md)コンパイラ オプションと[パック](../preprocessor/pack.md)プラグマは、メンバーの配置境界に影響します。

**sizeof**演算子は空のクラスの場合でも 0 を返しません。

**sizeof**演算子は、次のオペランドと共に使用できません。

- 関数 (ただし **、sizeof は**関数へのポインタに適用できます。

- ビット フィールド。

- 定義されていないクラス。

- タイプ**void**。

- 動的に割り当てられる配列。

- 外部配列。

- 不完全な型。

- かっこで囲まれた不完全な型の名前。

**sizeof**演算子が参照に適用されると **、sizeof が**オブジェクト自体に適用された場合と同じ結果になります。

サイズが大きでない配列が構造体の最後の要素である場合 **、sizeof**演算子は配列のない構造体のサイズを返します。

**sizeof**演算子は、多くの場合、次の形式の式を使用して配列内の要素の数を計算するために使用されます。

```cpp
sizeof array / sizeof array[0]
```

## <a name="see-also"></a>関連項目

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[Keywords](../cpp/keywords-cpp.md)
