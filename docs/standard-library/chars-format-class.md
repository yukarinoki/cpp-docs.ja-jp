---
title: chars_format 列挙型
ms.date: 07/22/2020
f1_keywords:
- charconv/std::chars_format
helpviewer_keywords:
- std::chars_format
ms.openlocfilehash: 4c1d495c943be02b66d52d1986a783b29a8009c5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230183"
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
| `scientific` | `from_chars()`が指数を予期して解析します。 書式指定子に似ています。たとえば、次 `'e'` `printf()` のような科学的表記法の形式です。`"1.729e+01"` |
| `fixed` | `from_chars()`は、指数を予期しない、または解析しないようにします。 これは、 `'f'` `printf()` などの浮動小数点形式の書式指定子に似てい `"17.29"` ます。|
| `hex` | は、 `from_chars()` 先頭に "0x" がない場合でも、16進数形式の数値を想定します。 |
| `general` | が `from_chars()` 指数を受け入れる (必要ではありません) ようにします。 `to_chars()`では、 `g` 関数は printf () 書式指定子に似ています。これは、科学的表記法または固定された形式に切り替わります。 指数の大きさを考慮して、適度にコンパクトな出力を生成できるようにします。 たとえば、は `1e-5` になり `"1e-05"` ますが、は `1e-4` になり `"0.001"` ます。 `1e5`の結果はになり `100000` ますが、はになり `1e6` `1e+06` ます。 `1e0``1`を生成します。|

## <a name="remarks"></a>解説

[From_chars](charconv-functions.md#from_chars)関数の場合、この列挙型はどのような種類の入力を必要とするかを示します。
[To_chars](charconv-functions.md#to_chars)関数の場合は、出力の種類を記述します。

## <a name="see-also"></a>関連項目

[\<charconv>](../standard-library/charconv.md)  
[printf () 書式指定子](..\c-runtime-library\format-specification-syntax-printf-and-wprintf-functions.md)
