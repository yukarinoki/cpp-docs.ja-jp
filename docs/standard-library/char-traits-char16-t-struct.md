---
title: char_traits&lt;char16_t&gt; 構造体
ms.date: 11/04/2016
f1_keywords:
- char_traits<char16_t>
- iosfwd/std::char_traits<char16_t>
helpviewer_keywords:
- char_traits<char16_t> class
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
ms.openlocfilehash: 53a77ff993d3a99cae1ec8e48a06dd7800ce74c7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230221"
---
# <a name="char_traitsltchar16_tgt-struct"></a>char_traits&lt;char16_t&gt; 構造体

テンプレート構造体**char_traits \<CharType> **型の要素に特殊化した構造体 **`char16_t`** 。

## <a name="syntax"></a>構文

```cpp
template <>
struct char_traits<char16_t>;
```

## <a name="remarks"></a>解説

特殊化により、構造体は、型のオブジェクトを操作するライブラリ関数を利用でき **`char16_t`** ます。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<string>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<string>](../standard-library/string.md)\
[char_traits 構造体](../standard-library/char-traits-struct.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
