---
description: '詳細情報: boyer_moore_horspool_searcher クラス'
title: boyer_moore_horspool_searcher クラス
ms.date: 08/03/2019
f1_keywords:
- functional/std::boyer_moore_horspool_searcher
helpviewer_keywords:
- std::boyer_moore_horspool_searcher [C++]
ms.openlocfilehash: 727af034dbb20bd1a0d09ae7de8f88da16a6ba36
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325426"
---
# <a name="boyer_moore_horspool_searcher-class"></a>boyer_moore_horspool_searcher クラス

クラスは、 `boyer_moore_horspool_searcher` ボイヤー-Horspool アルゴリズムを使用して、オブジェクトのコンストラクターで指定されたシーケンスを検索する関数オブジェクト型です。 検索は、オブジェクトの関数呼び出し演算子に渡された別のシーケンス内で実行されます。 このクラスは、 [std:: search](algorithm-functions.md#search)のオーバーロードのいずれかにパラメーターとして渡されます。

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

| メンバー | 説明 |
| - | - |
| **コンストラクター** | |
| [boyer_moore_horspool_searcher](#boyer-moore-horspool-searcher-constructor) | サーチャーインスタンスを構築します。 |
| **オペレーター** | |
| [operator ()](#operator-call) | シーケンスに対して操作を呼び出します。 |

## <a name="boyer_moore_horspool_searcher-constructor"></a><a name="boyer-moore-horspool-searcher-constructor"></a> boyer_moore_horspool_searcher コンストラクター

`boyer_moore_horspool_searcher`検索するシーケンス、ハッシュ関数オブジェクト、および等値述語を使用して、関数オブジェクトを構築します。

```cpp
boyer_moore_horspool_searcher(
    RandomAccessIterator pat_first,
    RandomAccessIterator pat_last,
    Hash hf = Hash(),
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>パラメーター

*pat_first*\
検索するシーケンスの最初の要素。

*pat_last*\
検索するシーケンスの末尾。

*hf*\
シーケンスの要素をハッシュするために使用される呼び出し可能オブジェクト。

*pred*\
Sequence 要素のオプションの等値比較述語。 等値比較型が指定されていない場合、既定値はに `std::equal_to` なります。

### <a name="remarks"></a>解説

*Binarypredicate*、 *Hash*、または *RandomAccessIterator* 型のコピーコンストラクター、または *Binarypredicate* または *Hash* の call 演算子によってスローされた例外をスローします。

このクラスは、C++ 17 で新しく追加されたものです。

## <a name="operator"></a><a name="operator-call"></a> operator ()

関数オブジェクトの呼び出し演算子。 引数シーケンス内で、 `[first, last)` コンストラクターに指定されたシーケンスを検索します。

```cpp
template <class ForwardIterator2>   // C++17
pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
    RandomAccessIterator2 first,
    RandomAccessIterator2 last) const;
```

### <a name="parameters"></a>パラメーター

*まずは*\
検索するシーケンスの最初の要素。

*前の*\
検索するシーケンスの末尾。

### <a name="remarks"></a>解説

検索パターンが空の場合、はを `[pat_first, pat_last)` 返し `make_pair(first, first)` ます。 検索パターンが見つからない場合は、を返し `make_pair(last, last)` ます。 それ以外の場合は、 `[first, last)` `[pat_first, pat_last)` 述語 *pred* に従って、に等しいシーケンスの先頭と末尾に反復子のペアを返します。

このクラスは、C++ 17 で新しく追加されたものです。

## <a name="see-also"></a>関連項目

[\<functional>](functional.md)\
[アルゴリズム関数](algorithm-functions.md)\
[boyer_moore_searcher クラス](boyer-moore-searcher-class.md)\
[std:: search](algorithm-functions.md#search)
