---
description: '詳細については、次を参照してください: forward_iterator_tag 構造体'
title: forward_iterator_tag 構造体
ms.date: 11/04/2016
f1_keywords:
- xutility/std::forward_iterator_tag
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
ms.openlocfilehash: 9b8b5ea7ff4e7d68c14c892d4ba6ef96f275b7da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324296"
---
# <a name="forward_iterator_tag-struct"></a>forward_iterator_tag 構造体

前方反復子を表す **iterator_category** 関数の戻り値の型を提供するクラス。

## <a name="syntax"></a>構文

```cpp
struct forward_iterator_tag    : public input_iterator_tag {};
```

## <a name="remarks"></a>解説

カテゴリ タグ クラスがアルゴリズムの選択にコンパイル タグとして使用されます。 テンプレート関数は、コンパイル時に最も効率的なアルゴリズムを利用できるように、その反復子引数の最も具体的なカテゴリを見つける必要があります。 型 `Iterator` の反復子ごとに、反復子の動作を表す最も具体的なカテゴリ タグとして `iterator_traits`< `Iterator`> **::iterator_category** を定義する必要があります。

 \< **Iter**> **Iter** が前方反復子として使用できるオブジェクトを表す場合、型は iterator **:: iterator_category** と同じです。

## <a name="example"></a>例

**iterator_tags** の使用方法の例については、「[iterator_traits](../standard-library/iterator-traits-struct.md)」または 「[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:**\<iterator>

**名前空間:** std

## <a name="see-also"></a>関連項目

[input_iterator_tag 構造体](../standard-library/input-iterator-tag-struct.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
