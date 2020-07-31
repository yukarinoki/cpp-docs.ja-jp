---
title: from_chars_result 構造体
ms.date: 7/23/2020
f1_keywords:
- std::from_chars_result
helpviewer_keywords:
- from_chars_result class
- from_chars_result structure
ms.openlocfilehash: 5a5dcfe6e5b59644e6ebf55d68ce43975e7d3c9d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215765"
---
# <a name="from_chars_result-struct"></a>from_chars_result 構造体

## <a name="syntax"></a>構文

```cpp
struct from_chars_result {
    const char* ptr;
    errc ec;
};
```

|メンバー|説明|
|--|--|
|`ptr`| `ec`がに等しい場合 `errc{}` 、変換は成功し、認識された `ptr` 数値の一部ではない最初の文字を指します。 |
|`ec` | 変換エラーコード。 特定のエラーコードについては、「」を参照してください [`errc`](system-error-enums.md#errc) 。|

### <a name="remarks"></a>解説

例: `"1729cats"` 10 進数の整数としての解析は成功し、は、が最初の非数字であり、が `ptr` `'c'` の1つ後ろでもあるを指し `"1729"` ます。

数字パターンに一致する文字がない場合、 `from_chars_result.ptr` はを指し、 `first` はに `from_chars_result.ec` `errc::invalid_argument` なります。

一部の文字のみが数値パターンに一致する場合は、 `from_chars_result.ptr` パターンに一致しない最初の文字を指します。または、すべての文字が一致する場合は、パラメーターの値を指定し `last` ます。

解析された値が変換後の型の範囲に収まらない場合、 `from_chars_result.ec` はに `errc::result_out_of_range` なります。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<charconv>

**名前空間:** std

**コンパイラオプション:** /std: c++ 17 以降が必要です。

## <a name="see-also"></a>関連項目

[from_chars](charconv-functions.md#from_chars)
