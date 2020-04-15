---
title: boyer_moore_horspool_searcherクラス
ms.date: 08/03/2019
f1_keywords:
- functional/std::boyer_moore_horspool_searcher
helpviewer_keywords:
- std::boyer_moore_horspool_searcher [C++]
ms.openlocfilehash: 4d404b414ad632e02be5f4e9fad0e22cefb86ce2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366774"
---
# <a name="boyer_moore_horspool_searcher-class"></a>boyer_moore_horspool_searcherクラス

この`boyer_moore_horspool_searcher`クラスは、ボイヤー-ムーア-ホースプール アルゴリズムを使用して、オブジェクトのコンストラクタで指定されたシーケンスを検索する関数オブジェクト型です。 検索は、オブジェクトの関数呼び出し演算子に提供される別のシーケンス内で行われます。 このクラスは、パラメーターとして[std::search](algorithm-functions.md#search)のオーバーロードの 1 つに渡されます。

## <a name="syntax"></a>構文

```cpp
template <
    class RandomAccessIterator,
    class Hash = hash<typename iterator_traits<RandomAccessIterator>::value_type>,
    class BinaryPredicate = equal_to<>>
class boyer_moore_horspool_searcher
{
    boyer_moore_horspool_searcher(
        RandomAccessIterator pat_first,
        RandomAccessIterator pat_last,
        Hash hf = Hash(),
        BinaryPredicate pred = BinaryPredicate());

    template <class RandomAccessIterator2>
    pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
        RandomAccessIterator2 first,
        RandomAccessIterator2 last) const;
};
```

## <a name="members"></a>メンバー

| | |
| - | - |
| **Constructor** | |
| [boyer_moore_horspool_searcher](#boyer-moore-horspool-searcher-constructor) | |
| **オペレーター** | |
| [Operator()](#operator-call) | |

## <a name="boyer_moore_horspool_searcher-constructor"></a><a name="boyer-moore-horspool-searcher-constructor"></a>boyer_moore_horspool_searcher コンストラクター

検索するシーケンス`boyer_moore_horspool_searcher`、ハッシュ関数オブジェクト、および等価述語を使用して、関数オブジェクトを構築します。

```cpp
boyer_moore_horspool_searcher(
    RandomAccessIterator pat_first,
    RandomAccessIterator pat_last,
    Hash hf = Hash(),
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>パラメーター

*pat_first*\
検索するシーケンスの初期要素。

*pat_last*\
検索するシーケンスの末尾。

*Hf*\
シーケンス要素のハッシュに使用される呼び出し可能オブジェクト。

*Pred*\
シーケンス要素の省略可能な等価比較述語。 等値比較の種類が指定されていない場合、既定値は`std::equal_to`です。

### <a name="remarks"></a>解説

*二項述語*、*ハッシュ*、または*RandomAccessIterator*型のコピー コンストラクター、または*BinaryPredicate*または*Hash*の呼び出し演算子によってスローされる例外をスローします。

このクラスは C++17 で新しく追加されました。

## <a name="operator"></a><a name="operator-call"></a>Operator()

関数オブジェクトの呼び出し演算子。 コンストラクタに指定されたシーケンス`[first, last)`を引数シーケンス内で検索します。

```cpp
template <class ForwardIterator2>   // C++17
pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
    RandomAccessIterator2 first,
    RandomAccessIterator2 last) const;
```

### <a name="parameters"></a>パラメーター

*まずは*\
検索するシーケンスの初期要素。

*前の*\
検索するシーケンスの末尾。

### <a name="remarks"></a>解説

検索パターン`[pat_first, pat_last)`が空の場合は、`make_pair(first, first)`を返します。 検索パターンが見つからない場合は、 を`make_pair(last, last)`返します。 それ以外の場合は、述語`[first, last)`*pred*に`[pat_first, pat_last)`従って等しいシーケンスの先頭と末尾に反復子のペアを返します。

このクラスは C++17 で新しく追加されました。

## <a name="see-also"></a>関連項目

[\<機能>](functional.md)\
[アルゴリズム関数](algorithm-functions.md)\
[boyer_moore_searcherクラス](boyer-moore-searcher-class.md)\
[std::検索](algorithm-functions.md#search)
