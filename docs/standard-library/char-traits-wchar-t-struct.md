---
title: char_traits&lt;wchar_t&gt; 構造体
ms.date: 11/04/2016
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
ms.openlocfilehash: 3b2504dbb124ccca7f9b27619585abb2b5795f92
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219171"
---
# <a name="char_traitsltwchar_tgt-struct"></a>char_traits&lt;wchar_t&gt; 構造体

テンプレート構造体を特殊化したクラスは、型の要素に** \<CharType> char_traits** **`wchar_t`** ます。

## <a name="syntax"></a>構文

```cpp
template <>
struct char_traits<wchar_t>;
```

## <a name="remarks"></a>解説

特殊化により、構造体は、この型のオブジェクトを操作するライブラリ関数を利用でき **`wchar_t`** ます。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<string>

**名前空間:** std

## <a name="see-also"></a>関連項目

[char_traits 構造体](../standard-library/char-traits-struct.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
