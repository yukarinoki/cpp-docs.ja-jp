---
description: '詳細については、次を参照してください: input_iterator_tag 構造体'
title: input_iterator_tag 構造体
ms.date: 11/04/2016
f1_keywords:
- xutility/std::input_iterator_tag
helpviewer_keywords:
- input_iterator_tag class
- input_iterator_tag struct
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
ms.openlocfilehash: 92bd110af71aecfa632b8e739126698eba457019
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231707"
---
# <a name="input_iterator_tag-struct"></a>input_iterator_tag 構造体

`iterator_category`入力反復子を表す関数の戻り値の型を提供するクラス。

## <a name="syntax"></a>構文

構造体 input_iterator_tag {} ;

## <a name="remarks"></a>解説

カテゴリ タグ クラスがアルゴリズムの選択にコンパイル タグとして使用されます。 テンプレート関数は、コンパイル時に最も効率的なアルゴリズムを利用できるように、その反復子引数の最も具体的なカテゴリを見つける必要があります。 型 `Iterator` の反復子ごとに、反復子の動作を表す最も具体的なカテゴリ タグとして `iterator_traits`< `Iterator`> **::iterator_category** を定義する必要があります。

型は、が \< **Iter**> 入力反復子として使用できるオブジェクトを表す場合に、iterator **:: iterator_category** と同じです `Iter` 。

## <a name="example"></a>例

の使用方法の例については、「 [iterator_traits](../standard-library/iterator-traits-struct.md) 」または「 [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) 」を参照してください `iterator_tag` 。

## <a name="requirements"></a>要件

**ヘッダー:**\<iterator>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
