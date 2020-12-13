---
description: '詳細については、次を参照してください: output_iterator_tag 構造体'
title: output_iterator_tag 構造体
ms.date: 11/04/2016
f1_keywords:
- xutility/std::output_iterator_tag
helpviewer_keywords:
- output_iterator_tag class
- output_iterator_tag struct
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
ms.openlocfilehash: 1bd97f88dc7ae68976920cf006cd10115b16b2f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340906"
---
# <a name="output_iterator_tag-struct"></a>output_iterator_tag 構造体

`iterator_category`出力反復子を表す関数の戻り値の型を提供するクラス。

## <a name="syntax"></a>構文

構造体 output_iterator_tag {} ;

## <a name="remarks"></a>解説

カテゴリ タグ クラスがアルゴリズムの選択にコンパイル タグとして使用されます。 テンプレート関数は、コンパイル時に最も効率的なアルゴリズムを利用できるように、その反復子引数の最も具体的なカテゴリを見つける必要があります。 型 `Iterator` の反復子ごとに、反復子の動作を表す最も具体的なカテゴリ タグとして `iterator_traits`< `Iterator`> **::iterator_category** を定義する必要があります。

型は、が \< **Iter**> 出力反復子として使用できるオブジェクトを表す場合に、iterator **:: iterator_category** と同じです。 `Iter`

このタグは、出力反復子には `value_type` または `difference_type` がないため、他の反復子タグと同様、反復子の `value_type` または `difference_type` でパラメーター化されません。

## <a name="example"></a>例

の使用方法の例については、「 [iterator_traits](../standard-library/iterator-traits-struct.md) 」または「 [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) 」を参照してください `iterator_tag` 。

## <a name="requirements"></a>要件

**ヘッダー:**\<iterator>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
