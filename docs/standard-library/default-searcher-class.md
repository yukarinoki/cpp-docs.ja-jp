---
title: default_searcherクラス
ms.date: 08/03/2019
f1_keywords:
- functional/std::default_searcher
helpviewer_keywords:
- std::default_searcher [C++]
ms.openlocfilehash: 2c8b93b83b271f787c993f789e1a68f84a60f016
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368926"
---
# <a name="default_searcher-class"></a>default_searcherクラス

A`default_searcher`は、オブジェクトのコンストラクターで指定されたシーケンスを検索する操作の関数オブジェクト型です。 検索は、オブジェクトの関数呼び出し演算子に提供される別のシーケンス内で行われます。 検索`default_searcher`を実行するために[std::search](algorithm-functions.md#search)を呼び出します。

## <a name="syntax"></a>構文

```cpp
template <class ForwardIterator, class BinaryPredicate = equal_to<>>
class default_searcher
{
    default_searcher(
        ForwardIterator pat_first,
        ForwardIterator pat_last,
        BinaryPredicate pred = BinaryPredicate());

    template <class ForwardIterator2>
    pair<ForwardIterator2, ForwardIterator2> operator()(
        ForwardIterator2 first,
        ForwardIterator2 last) const;
};
```

## <a name="members"></a>メンバー

| | |
| - | - |
| **Constructor** | |
| [default_searcher](#default-searcher-constructor) | |
| **オペレーター** | |
| [Operator()](#operator-call) | |

## <a name="default_searcher-constructor"></a><a name="default-searcher-constructor"></a>default_searcherコンストラクター

検索する`default_searcher`シーケンスと等価述語を使用して、関数オブジェクトを構築します。

```cpp
default_searcher(                   // C++17
    ForwardIterator pat_first,
    ForwardIterator pat_last,
    BinaryPredicate pred = BinaryPredicate());

constexpr default_searcher(         // C++20
    ForwardIterator pat_first,
    ForwardIterator pat_last,
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>パラメーター

*pat_first*\
検索するシーケンスの初期要素。

*pat_last*\
検索するシーケンスの末尾。

*Pred*\
シーケンス要素の省略可能な等価比較述語。 等値比較の種類が指定されていない場合、既定値は`std::equal_to`です。

### <a name="remarks"></a>解説

*BinaryPredicate*型または*ForwardIterator*型のコピー コンストラクターによってスローされた例外をスローします。

このクラスは C++17 で新しく追加されました。 C++ 20 は`constexpr`、コンストラクターを作成しました。

## <a name="operator"></a><a name="operator-call"></a>Operator()

関数演算子の呼び出し演算子。 コンストラクタに指定されたシーケンス`[first, last)`を引数シーケンス内で検索します。

```cpp
template <class ForwardIterator2>   // C++17
pair<ForwardIterator2, ForwardIterator2> operator()(
    ForwardIterator2 first,
    ForwardIterator2 last) const;

template <class ForwardIterator2>   // C++20
constexpr pair<ForwardIterator2, ForwardIterator2> operator()(
    ForwardIterator2 first,
    ForwardIterator2 last) const;
```

### <a name="parameters"></a>パラメーター

*まずは*\
検索するシーケンスの初期要素。

*前の*\
検索するシーケンスの末尾。

### <a name="remarks"></a>解説

反復子のペアを返します。 イテレータ i*は*、次の有効な結果です。

`std::search( first, last, pat_first, pat_last, pred )`.

ペアの 2 番目の反復子は *、i** が*最後*の場合は*最後です*。 それ以外の場合は、次の結果が有効です。

`std::next( i, std::distance( pat_first, pat_last ))`.

このクラスは C++17 で新しく追加されました。 C++ 20 は、`constexpr`呼び出し演算子を行いました。

## <a name="see-also"></a>関連項目

[\<機能>](functional.md)\
[アルゴリズム関数](algorithm-functions.md)\
[std::検索](algorithm-functions.md#search)
