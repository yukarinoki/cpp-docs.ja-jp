---
description: '詳細については、次を参照してください: from_chars_result 構造体'
title: from_chars_result 構造体
ms.date: 7/23/2020
f1_keywords:
- std::from_chars_result
helpviewer_keywords:
- from_chars_result class
- from_chars_result structure
ms.openlocfilehash: 894a687a4395e22538b384675af5b4ce57731f78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232279"
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

## <a name="requirements"></a>要件

**ヘッダー:**\<charconv>

**名前空間:** std

**コンパイラオプション:** /std: c++ 17 以降が必要です。

## <a name="see-also"></a>関連項目

[from_chars](charconv-functions.md#from_chars)
