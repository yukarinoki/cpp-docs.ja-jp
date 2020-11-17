---
title: 型修飾子
description: Microsoft Visual C コンパイラで使用される C 言語の型修飾子について説明します
ms.date: 11/6/2020
helpviewer_keywords:
- volatile keyword [C], type qualifier
- type qualifiers
- volatile keyword [C]
- qualifiers for types
- const keyword [C]
- memory, access using volatile
- volatile keyword [C], type specifier
ms.assetid: bb4c6744-1dd7-40a8-b4eb-f5585be30908
ms.openlocfilehash: dd36aeb5d142eebbd6e4a339fe6c18925a6fd45a
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381611"
---
# <a name="type-qualifiers"></a>型修飾子

型修飾子は、2 つのうちいずれかの特性を識別子に割り当てます。 **`const`** 型修飾子は、変更不可能なオブジェクトを宣言します。 **`volatile`** 型修飾子は、同時実行されるスレッドなど、そのプログラムの制御範囲以外の要素によって値を変更できる項目を宣言します。

型修飾子 **`const`** 、 **`restrict`** 、 **`volatile`** は、宣言内で 1 回だけ使用できます。 型修飾子は型指定子との併用が可能ですが、複数項目宣言で、最初のコンマの後にこれらを指定することはできません。 たとえば、次の宣言は有効です。

```c
typedef volatile int VI;
const int ci;
```

次の宣言は無効です。

```c
typedef int *i, volatile *vi;
float f, const cf;
```

型修飾子が意味を持つのは、式の左辺値として識別子にアクセスする場合のみです。 左辺値および式の詳細については、「[左辺値と右辺値の式](../c-language/l-value-and-r-value-expressions.md)」を参照してください。

## <a name="syntax"></a>構文

*`type-qualifier`*:\
&emsp;**`const`**\
&emsp;**`restrict`**\
&emsp;**`volatile`**

## <a name="const-and-volatile"></a>`const` および `volatile`

有効な **`const`** と **`volatile`** の宣言を次に示します。

```c
int const *p_ci;      // Pointer to constant int
int const (*p_ci);   // Pointer to constant int
int *const cp_i;     // Constant pointer to int
int (*const cp_i);   // Constant pointer to int
int volatile vint;     // Volatile integer
```

配列型の指定に型修飾子が含まれる場合、要素は修飾されますが、配列型は修飾されません。 関数型の指定に修飾子が含まれる場合、その動作は未定義になります。 **`volatile`** と **`const`** はいずれも、オブジェクトの値の範囲または算術的特性に影響を与えません。

- **`const`** キーワードを使用できるのは、基本型、集約型、任意の型のオブジェクトへのポインター、または **`typedef`** を変更する場合です。 **`const`** 型修飾子のみを使用して項目を宣言した場合、その型は **const int** になります。 **`const`** 変数は初期化できます。また、ストレージの読み取り専用領域に配置できます。 **`const`** へのポインターを宣言する場合に **`const`** キーワードを使用すると便利です。この方法でポインターを宣言すると、関数がそのポインターを一切変更できなくなります。

- プログラムのどの時点でも、未知のプロセスが **`volatile`** 変数にアクセスし、その値を使用または変更できるとコンパイラでは見なされます。 コマンド ラインで指定した最適化にかかわらず、 **`volatile`** 変数に値を割り当てたり参照したりするコードが必ず (それが何も影響しない場合でも) 生成されます。

**`volatile`** を単独で使用した場合、 **`int`** を指定したと見なされます。 **`volatile`** 型指定子を使用すれば、特別なメモリ位置へ確実にアクセスできます。 シグナル ハンドラー、同時実行のプログラム、または特殊なハードウェア (メモリ マップト I/O 制御レジスタなど) がアクセスまたは変更できるデータ オブジェクトで **`volatile`** を使用します。 変数が有効な間だけ **`volatile`** として宣言するか、または 1 つの参照を **`volatile`** にキャストできます。

- 項目は **`const`** と **`volatile`** の両方であってもかまいません。その場合、自身のプログラムではその項目を変更できませんが、非同期のプロセスでは変更できます。
 
## `restrict`

C99 で導入された **`restrict`** 型修飾子は、ポインター宣言に適用できます。 ポインターが指し示しているものではなく、ポインターが修飾されます。

**`restrict`** は、現在のスコープ内の他のポインターによって同じメモリ位置が参照されていないことを示す、コンパイラへの最適化ヒントです。 つまり、そのポインターまたはそれから派生した値 (ポインター + 1 など) のみが、ポインターの有効期間中にオブジェクトにアクセスするために使用されます。 これは、コンパイラでより最適化されたコードを生成するのに役立ちます。 C++ には同等のメカニズムとして [`__restrict`](../cpp/extension-restrict.md) があります

**`restrict`** は、ユーザーとコンパイラの間の取り決めであることに注意してください。 **`restrict`** でマークされたポインターのエイリアスを作成した場合、結果は未定義になります。

**`restrict`** を使用する例を次に示します。

```c
void test(int* restrict first, int* restrict second, int* val)
{
    *first += *val;
    *second += *val;
}

int main()
{
    int i = 1, j = 2, k = 3;
    test(&i, &j, &k);

    return 0;
}

// Marking union members restrict tells the compiler that
// only z.x or z.y will be accessed in any scope, which allows
// the compiler to optimize access to the members.
union z 
{
    int* restrict x;
    double* restrict y;
};
```

## <a name="see-also"></a>関連項目

[`/std` (言語の標準バージョンの指定)](../build/reference/std-specify-language-standard-version.md)\
[宣言と型](../c-language/declarations-and-types.md)
