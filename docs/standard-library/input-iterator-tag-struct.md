---
title: input_iterator_tag 構造体
ms.date: 11/04/2016
f1_keywords:
- xutility/std::input_iterator_tag
helpviewer_keywords:
- input_iterator_tag class
- input_iterator_tag struct
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
ms.openlocfilehash: 5478a8f9fa6013202a1ea8dd838eedb80b9c367e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493929"
---
# <a name="inputiteratortag-struct"></a>input_iterator_tag 構造体

戻り値の型を提供するクラス`iterator_category`入力反復子を表す関数。

## <a name="syntax"></a>構文

構造体 input_iterator_tag {};

## <a name="remarks"></a>Remarks

カテゴリ タグ クラスはアルゴリズムの選択にコンパイル タグとして使用されます。 テンプレート関数は、コンパイル時に最も効率的なアルゴリズムを利用できるように、その反復子引数の最も具体的なカテゴリを見つける必要があります。 `Iterator` 型の反復子ごとに、反復子の動作を表す最も具体的なカテゴリ タグとして `iterator_traits`< `Iterator`> **::iterator_category** を定義する必要があります。

型が同じ**反復子**\< **Iter**> **:::iterator_category**とき`Iter`として使用できるオブジェクトについて説明します、入力反復子。

## <a name="example"></a>例

参照してください[iterator_traits](../standard-library/iterator-traits-struct.md)または[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)を使用する方法の例については`iterator_tag`s。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<iterator>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
