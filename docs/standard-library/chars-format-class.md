---
description: '詳細情報: chars_format 列挙型'
title: chars_format 列挙型
ms.date: 08/03/2020
f1_keywords:
- charconv/std::chars_format
helpviewer_keywords:
- std::chars_format
ms.openlocfilehash: af458f96e3e9dbe4db9d1adab1c529403cefcaa6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325182"
---
# <a name="chars_format-enum"></a>chars_format 列挙型

ライブラリと共に使用 [\<charconv>](charconv.md) して、プリミティブ数値変換の浮動小数点形式を指定します。

## <a name="syntax"></a>構文

```cpp
enum class chars_format {
    scientific = unspecified,
    fixed = unspecified,
    hex = unspecified,
    general = fixed | scientific
};
```

### <a name="members"></a>メンバー

|要素|説明|
|-|-|
| `scientific` | `from_chars()`が指数を予期して解析します。 書式指定子に似ています。これは、 `printf()` `'e'` のような科学的表記法の形式です `"1.729e+01"` 。 |
| `fixed` | `from_chars()`は、指数を予期しない、または解析しないようにします。 これは、 `printf()` のように、浮動小数点形式の書式指定子に似てい `'f'` `"17.29"` ます。|
| `hex` | は、 `from_chars()` 16 進数形式の数値を想定しますが、先頭は使用しません `0x` 。 |
| `general` | が `from_chars()` 指数を受け入れる (必要ではありません) ようにします。 `to_chars()`では、書式指定子に似てい `printf()` ます。これは `'g'` 、指数表記または固定された形式に切り替わります。 指数の大きさを考慮して、適度にコンパクトな出力を生成できるようにします。 たとえば、は `1e-5` になり `"1e-05"` ますが、は `1e-4` になり `"0.001"` ます。 `1e5` の結果はになり `100000` ますが、はになり `1e6` `1e+06` ます。 `1e0``1`を生成します。|

## <a name="remarks"></a>解説

[From_chars](charconv-functions.md#from_chars)関数の場合、この列挙型はどのような種類の入力を必要とするかを示します。
[To_chars](charconv-functions.md#to_chars)関数の場合は、出力の種類を記述します。

## <a name="requirements"></a>要件

**ヘッダー:**\<charconv>

**名前空間:** std

/std: c++ 17 以降が必要です。

## <a name="see-also"></a>関連項目

[\<charconv>](../standard-library/charconv.md)  
[printf () 書式指定子](..\c-runtime-library\format-specification-syntax-printf-and-wprintf-functions.md)
