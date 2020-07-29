---
title: default_searcher クラス
ms.date: 08/03/2019
f1_keywords:
- functional/std::default_searcher
helpviewer_keywords:
- std::default_searcher [C++]
ms.openlocfilehash: 3b5b05dfa2613f9eeaaa18fa8066bcd44f57d1be
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203729"
---
# <a name="default_searcher-class"></a>default_searcher クラス

は、 `default_searcher` オブジェクトのコンストラクターで指定されたシーケンスを検索する操作の関数オブジェクト型です。 検索は、オブジェクトの関数呼び出し演算子に渡された別のシーケンス内で実行されます。 は `default_searcher` 、 [std:: search](algorithm-functions.md#search)を呼び出して検索を実行します。

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
| **コンストラクター** | |
| [default_searcher](#default-searcher-constructor) | |
| **オペレーター** | |
| [operator ()](#operator-call) | |

## <a name="default_searcher-constructor"></a><a name="default-searcher-constructor"></a>default_searcher コンストラクター

`default_searcher`検索するシーケンスと等値述語を使用して、関数オブジェクトを構築します。

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
検索するシーケンスの最初の要素。

*pat_last*\
検索するシーケンスの末尾。

*pred*\
Sequence 要素のオプションの等値比較述語。 等値比較型が指定されていない場合、既定値はに `std::equal_to` なります。

### <a name="remarks"></a>解説

*Binarypredicate*型または*ForwardIterator*型のコピーコンストラクターによってスローされた例外をスローします。

このクラスは、C++ 17 で新しく追加されたものです。 C++ 20 によってコンストラクターが作成されました **`constexpr`** 。

## <a name="operator"></a><a name="operator-call"></a>operator ()

関数演算子の呼び出し演算子。 引数シーケンス内で、 `[first, last)` コンストラクターに指定されたシーケンスを検索します。

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
検索するシーケンスの最初の要素。

*前の*\
検索するシーケンスの末尾。

### <a name="remarks"></a>解説

反復子のペアを返します。 最初の反復子*i*は、次のような結果になります。

`std::search( first, last, pat_first, pat_last, pred )`.

ペアの2番目の反復子は、 *i** が*last*の場合は*last*です。 それ以外の場合は、次のような結果になります。

`std::next( i, std::distance( pat_first, pat_last ))`.

このクラスは、C++ 17 で新しく追加されたものです。 C++ 20 は呼び出し演算子を作成しました **`constexpr`** 。

## <a name="see-also"></a>関連項目

[\<functional>](functional.md)\
[アルゴリズム関数](algorithm-functions.md)\
[std:: search](algorithm-functions.md#search)
