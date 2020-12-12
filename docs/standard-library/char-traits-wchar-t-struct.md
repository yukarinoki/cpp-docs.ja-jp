---
description: 詳細については、「char_traits &lt; wchar_t 構造体」を参照してください。 &gt;
title: char_traits&lt;wchar_t&gt; 構造体
ms.date: 11/04/2016
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
ms.openlocfilehash: 0276f4b50cb0039d0bec49b1b3eb2a0b3b2463aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325223"
---
# <a name="char_traitsltwchar_tgt-struct"></a>char_traits&lt;wchar_t&gt; 構造体

テンプレート構造体を特殊化したクラスは、型の要素に **\<CharType> char_traits** **`wchar_t`** ます。

## <a name="syntax"></a>構文

```cpp
template <>
struct char_traits<wchar_t>;
```

## <a name="remarks"></a>解説

特殊化により、構造体は、この型のオブジェクトを操作するライブラリ関数を利用でき **`wchar_t`** ます。

## <a name="requirements"></a>要件

**ヘッダー:**\<string>

**名前空間:** std

## <a name="see-also"></a>関連項目

[char_traits 構造体](../standard-library/char-traits-struct.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
