---
title: sizeof 演算子 (C)
ms.date: 11/04/2016
f1_keywords:
- sizeof
helpviewer_keywords:
- sizeof operator
ms.assetid: 70826d03-3451-41e4-bebb-a820ae66d53f
ms.openlocfilehash: 1d06fc8b541cbce3771a485c8f71953be8f7d552
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229520"
---
# <a name="sizeof-operator-c"></a>sizeof 演算子 (C)

**`sizeof`** 演算子によって、オペランドの型のオブジェクトを格納するために必要なストレージの量をバイト単位で取得できます。 この演算子を使うと、コンピューターに依存するデータ サイズをプログラムで指定せずに済みます。

## <a name="syntax"></a>構文

```
sizeof unary-expression
sizeof ( type-name )
```

## <a name="remarks"></a>Remarks

オペランドは、*unary-expression* の識別子、または型のキャスト式 (つまり、かっこで囲まれた型指定子) のいずれかです。 *unary-expression* は、ビット フィールド オブジェクト、不完全な型、または関数指定子を表すことはできません。 結果は、符号なしの整数定数です。 標準ヘッダー STDDEF.H は、この型を **size_t** として定義します。

配列識別子に **`sizeof`** 演算子を適用した場合、結果は配列識別子によって表されるポインターのサイズではなく、配列全体のサイズとなります。

構造体または共用体の型名、または構造体または共用体の型の識別子に対して **`sizeof`** 演算子を適用した場合、結果は、内部と末尾の埋め込みを含む構造体または共用体のバイト数となります。 このサイズには、構造体または共用体のメンバーをメモリ境界に配置するために使用される内部および末尾の埋め込みが含まれる場合があります。 したがって、結果は、個々のメンバーのストレージ要件を加算して計算されたサイズには必ずしも対応しません。

可変長配列が構造の最後の要素である場合、 **`sizeof`** 演算子は配列のない構造体のサイズを返します。

```
buffer = calloc(100, sizeof (int) );
```

この例では、コンピューターごとに異なる **`int`** のサイズを `calloc` という名前のランタイム関数に引数として渡すために、 **`sizeof`** 演算子を使用します。 関数によって返された値は `buffer` に格納されます。

```
static char *strings[] = {
      "this is string one",
      "this is string two",
      "this is string three",
   };
const int string_no = ( sizeof strings ) / ( sizeof strings[0] );
```

この例では、`strings` は **`char`** へのポインターの配列です。 ポインターの数は、配列の要素の数ですが、指定されていません。 **`sizeof`** 演算子を使用して配列の要素数を計算し、ポインターの数を簡単に決定できます。 **`const`** の整数値 `string_no` は、この数に初期化されます。 **`const`** 値であるため、`string_no` は変更できません。

## <a name="see-also"></a>関連項目

[C 演算子](c-operators.md)<br/>
[C++ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
