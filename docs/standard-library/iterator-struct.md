---
description: '詳細情報: iterator 構造体'
title: iterator 構造体
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
ms.openlocfilehash: 81a35fd749b3393a0235fdac8c4bf13a1ef5af79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254327"
---
# <a name="iterator-struct"></a>iterator 構造体

ユーザー定義の反復子クラスが s で正常に動作するようにするために使用される空の基本構造体 `iterator_trait` 。

## <a name="syntax"></a>構文

```cpp
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };
```

## <a name="remarks"></a>解説

このテンプレート構造体は、すべての反復子の基本データ型として機能します。 これは、メンバーの型を定義します。

- `iterator_category` (テンプレート パラメーター `Category` のシノニム)。

- `value_type` (テンプレート パラメーター `Type` のシノニム)。

- `difference_type` (テンプレート パラメーター `Distance` のシノニム)。

- `distance_type` (テンプレート パラメーター `Distance` のシノニム)。

- `pointer` (テンプレート パラメーター `Pointer` のシノニム)。

- `reference` (テンプレート パラメーター `Reference` のシノニム)。

`value_type`と参照がのオブジェクトを指す場合でも、を定数型にすることはできません `pointer` **`const`** `Type` **`const`** `Type` 。

## <a name="example"></a>例

反復子の基底クラスの型の宣言方法や使用例については、「[iterator_traits](../standard-library/iterator-traits-struct.md)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:**\<iterator>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<iterator>](../standard-library/iterator.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
