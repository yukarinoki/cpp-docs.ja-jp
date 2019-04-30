---
title: char_traits&lt;char16_t&gt; 構造体
ms.date: 11/04/2016
f1_keywords:
- char_traits<char16_t>
- iosfwd/std::char_traits<char16_t>
helpviewer_keywords:
- char_traits<char16_t> class
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
ms.openlocfilehash: def0023b259a7b4816bdda29684c1dd9853d5f5b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62379533"
---
# <a name="chartraitsltchar16tgt-struct"></a>char_traits&lt;char16_t&gt; 構造体

テンプレート構造体 **char_traits\<CharType>** を `char16_t` 型の要素に特殊化した構造体。

## <a name="syntax"></a>構文

```cpp
template <>
struct char_traits<char16_t>;
```

## <a name="remarks"></a>Remarks

特殊化により、構造体で型 `char16_t` のオブジェクトを操作するライブラリ関数を利用できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<string>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<string>](../standard-library/string.md)<br/>
[char_traits 構造体](../standard-library/char-traits-struct.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
