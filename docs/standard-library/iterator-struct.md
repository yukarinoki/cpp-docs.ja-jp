---
title: iterator 構造体
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
ms.openlocfilehash: b45cdb5c3d4608296cca34ad6a0be6e25b588d28
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222304"
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

## <a name="requirements"></a>必要条件

**ヘッダー:**\<iterator>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<iterator>](../standard-library/iterator.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
