---
title: to_chars_result 構造体
ms.date: 07/22/2020
f1_keywords:
- charconv/std::to_chars_result
helpviewer_keywords:
- to_chars_result class
- to_chars_result structure
ms.openlocfilehash: 4e46d1cc9d0b6a02d731ad25c2e85c99300d7234
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509653"
---
# <a name="to_chars_result-struct"></a>to_chars_result 構造体

## <a name="syntax"></a>構文

```cpp
struct to_chars_result {
    char* ptr;
    errc ec;
};
```

## <a name="members"></a>メンバー

|メンバー|説明|
|--|--|
|`ptr`| `ec`がに等しい場合 `errc{}` 、変換は成功し、 `ptr` は書き込み文字の1つ後ろのポインターになります。 それ以外の場合、に `ptr` はパラメーターの値があり、 `to_chars()` `last` 最初の範囲の内容が指定されてい \[ ません。|
|`ec` | 変換エラーコード。 特定のエラーコードについては、「」を参照してください [`errc`](system-error-enums.md#errc) 。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<charconv>

**名前空間:** std

**コンパイラオプション:** /std: c++ 17 以降が必要です。

## <a name="see-also"></a>関連項目

[to_chars](charconv-functions.md#to_chars)
