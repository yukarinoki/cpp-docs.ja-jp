---
title: <ranges>
description: 標準テンプレートライブラリ (STL) の範囲ライブラリの概要
ms.date: 04/13/2021
f1_keywords:
- <ranges>
helpviewer_keywords:
- ranges
ms.openlocfilehash: 45f27b5e2e569a27f81fc950e8902ad67a69c6fd
ms.sourcegitcommit: bac5dde649d5b0447de1d26a73365e36d74595f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "107381730"
---
# `<ranges>`

大まかに言えば、範囲は反復処理することができます。 範囲は、標準テンプレートライブラリ (STL) を使用する機能を簡略化および増幅する方法で反復子を抽象化します。

通常、STL アルゴリズムでは、操作する必要があるコレクションの部分を指す反復子を受け取ります。 現在のを並べ替える方法を検討してください `vector` 。 を呼び出すには、の `std::sort()` 先頭と末尾を示す2つの反復子を渡し `vector` ます。 これにより柔軟性が向上しますが、反復子をアルゴリズムに渡すことは、ほとんどの場合、全体を単純に並べ替える必要があるため、余分なノイズです。

範囲の場合は、単にを呼び出すことができます `std::ranges::sort(myVector);` 。これは、範囲ライブラリで呼び出されたものとして扱われ `std::sort(myVector.begin(), myVector.end());` 、アルゴリズムはパラメーターとして範囲を受け取ります (ただし、必要に応じて反復子も取得できます)。 で使用できる範囲アルゴリズムの例として、、、、、、、、、 `<algorithm>` `copy` `copy_n` `copy_if` `all_of` `any_of` `none_of` `find` `find_if` 、 `find_if_not` 、、 `count` `count_if` `for_each` `for_each_n` `equal` `mismatch` 、、およびがあります。

記述が容易で読みやすく、コードの方が優れていますが、範囲の利点はさらに大きくなります。 また、STL アルゴリズムをより簡単に作成できるようにすることで、データのコレクションを簡単にフィルター処理したり変換したりすることができます。

範囲はコンテナーのような要素を所有していないため、軽量です。 範囲のコピー、移動、または割り当てにかかる時間は、その範囲が指す要素の数に関係なく一定です。

## <a name="a-ranges-example"></a>範囲の例

範囲の前に、特定の条件に一致するコレクションの要素のみを変換する場合は、操作間で結果を保持するための中間手順を導入する必要があります。 たとえば、3で割り切れる別のベクトル内の要素のみから二乗のベクターを構築するとします。 次のようなコードを記述します。

```cpp
std::vector<int> input = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
std::vector<int> intermediate, output;

std::copy_if(input.begin(), input.end(), std::back_inserter(intermediate), [](const int i) { return i%3 == 0; });
std::transform(intermediate.begin(), intermediate.end(), std::back_inserter(output), [](const int i) {return i*i; });
```

範囲では、ベクターを使用しなくても同じことを実現でき `intermediate` ます。

```cpp
// requires /std:c++latest
std::vector<int> input = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

auto output = input | std::views::filter([](const int n) {return n % 3 == 0; }) | std::views::transform([](const int n) {return n * n; });
```  

読みやすくするだけでなく、ベクターとそのコンテンツに必要なメモリ割り当てを回避し、 `intermediate` 2 つの操作を構成することもできます。

上記のコードでは、3で割り切れた各要素は、その要素を二乗する演算と組み合わされています。 ' `|` ' シンボルは操作をまとめて、左から右に読み取ります。

結果は、 `output` それ自体がビューと呼ばれる範囲の型になります。これについては次に説明します。

> [!NOTE]
> 範囲の例では、 [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) コンパイラオプションが必要です。

## <a name="views"></a>ビュー

ビューは、実質的には別の範囲を取得し、その要素がどのようにアクセスされるかを変換する範囲です。 要素の表示方法は、指定したアルゴリズムまたは操作によって異なります。 基になる範囲が変更されていません。 前の例では、1つのビューは範囲を受け取り、3で割り切れる要素のみのビューを返していました。

ビューは軽量です。 範囲と同様に、要素は所有しません。 ビューのコピー、移動、または割り当てにかかる時間は、そのビューが指す要素の数に関係なく、定数になります。

ビューは、コンポーザブルです。 上の例では、3で割り切れるベクター要素のビューが、これらの要素を二乗するビューと結合されています。

ビューの要素は遅延的に評価されます。 つまり、ビュー内の要素を生成するために適用する変換は、要素を要求するまで評価されません。 たとえば、デバッガーで次のコードを実行し、との行にブレークポイントを設定した場合は、 `auto divisible_by_three = ...` `auto square =  ...` `divisible_by_three` の各要素 `input` が 3 divisibility に対してテストされるため、ラムダブレークポイントにヒットしたことがわかります。 `square`3 で割り切れた要素は2乗されているため、ラムダブレークポイントはヒットします。

```cpp
// requires /std:c++latest
#include <ranges>
#include <vector>
#include <iostream>

int main()
{
    std::vector<int> input =  { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    auto divisible_by_three = [](const int n) {return n % 3 == 0; };
    auto square = [](const int n) {return n * n; };

    auto x = input | std::views::filter(divisible_by_three)
                   | std::views::transform(square);

    for (int i : x)
    {
        std::cout << i << '\n';
    }
    return 0;
}
```

## <a name="view-adaptors"></a>アダプターの表示

ビューアダプタでは、範囲に対するビューが生成されます。 表示されている範囲は変更されません。 ビューは要素を所有していません。 これにより、指定したカスタマイズされた動作を使用して、基になる範囲を反復処理することができます。

上の例では、最初のビューは、3で割り切れるの要素のみを提供する反復子と同じように動作し `input` ます。 もう1つのビューは、3で割り切れた要素を受け取り、要素の正方形を提供する反復子のように動作します。

`<ranges>`ライブラリには、さまざまな種類のビューアダプターが用意されています。 フィルターおよび変換ビューに加えて、範囲の最初の N 個の要素を取得またはスキップするビュー、範囲の順序、結合範囲、条件が満たされるまで範囲の要素をスキップするビュー、範囲の要素を変換するビューなどがあります。

## <a name="range-adaptors"></a>範囲アダプター

範囲アダプターは、既存の範囲から新しい範囲を生成します。 新しい範囲では、範囲アダプターによって指定されたカスタム動作を使用して、要素を指定します。 たとえば、範囲アダプターは範囲を受け取り、元の範囲の要素を逆順に表示する新しいものを生成する場合があります。 前に説明したビューは、一般的な種類の範囲アダプターです。

範囲アダプターは、遅延評価された範囲を生成します。 つまり、範囲内のすべての要素を変換するコストは発生しません。これは、アクセスした要素とアクセスした時点の要素だけです。

範囲アダプターにはさまざまな形式があります。 たとえば、範囲アダプターを使用すると、述語 () に基づいて別の範囲をフィルター処理したり、範囲 `view::filter` 内の要素 () を変換したり、範囲 () を分割したりすることができ `view::transform` `view::split()` ます。

範囲アダプターは、チェーンまたは構成することができます。この場合、範囲の強力で柔軟性が最も顕著になります。

## <a name="range-algorithms"></a>範囲アルゴリズム

範囲の引数を受け取る範囲アルゴリズムが作成されました。 たとえば、`std::ranges::sort(myVector);` のように指定します。

範囲アルゴリズムは、要素がアクセスされたときにのみ範囲で動作することを意味するレイジーです。 コンテナーで直接操作することができ、簡単に連結できます。

## <a name="types-of-ranges"></a>範囲の種類

範囲を使用してできることは、その範囲の基になる反復子の型によって異なります。 絞り込みと呼ばれるさまざまな種類の範囲があります。 さまざまな種類の範囲は、C++ 20 の概念として体系化ます。 次の表に、さまざまな範囲の概念と、適用できるコンテナーの種類を示します。

| 範囲の洗練 | 説明 | サポートされているコンテナー |
|--|--|--|
| `std::ranges::input_range` | 最初から最後まで反復処理できます |
| `std::forward_list`<br>`std::unordered_map`<br>`std::unordered_multimap`<br>`std::unordered_set`<br>`std::unordered_multiset`<br>`basic_istream_view` |
| `std::ranges::forward_range` | 最初から最後まで繰り返し反復処理できます) | `std::forward_list`<br>`std::unordered_map`<br>`std::unordered_multimap`<br>`std::unordered_set`<br>`std::unordered_multiset` |
| `std::ranges::bidirectional_range` | 前方と後方を複数回繰り返すことができます | `std::list`<br>`std::map`<br>`std::multimap`<br>`std::multiset`<br>`std::set`|
| `std::ranges::random_access_range` | 演算子を使用して、任意の要素に (一定時間) アクセスできます `[]` 。 | `std::deque` |
| `std::ranges::contiguous_range` | 要素はメモリに連続して格納されます。 | `std::array`<br>`std::string`<br>`std::vector` |

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)