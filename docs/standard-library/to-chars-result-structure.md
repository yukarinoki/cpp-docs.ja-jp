---
description: '詳細については、次を参照してください: to_chars_result 構造体'
title: to_chars_result 構造体
ms.date: 07/22/2020
f1_keywords:
- charconv/std::to_chars_result
helpviewer_keywords:
- to_chars_result class
- to_chars_result structure
ms.openlocfilehash: fb043ba928f086549aea326419ec3a2d673723ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167189"
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

## <a name="requirements"></a>要件

**ヘッダー:**\<charconv>

**名前空間:** std

**コンパイラオプション:** /std: c++ 17 以降が必要です。

## <a name="see-also"></a>関連項目

[to_chars](charconv-functions.md#to_chars)
