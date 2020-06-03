---
title: __pctype_func
ms.date: 4/2/2020
api_name:
- __pctype_func
- _o___pctype_func
api_location:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __pctype_func
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
ms.openlocfilehash: 67447823b0322e647784cdbe0f3f7228e1c5fb34
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919246"
---
# <a name="__pctype_func"></a>__pctype_func

文字分類情報の配列へのポインターを取得します。

## <a name="syntax"></a>構文

```cpp
const unsigned short *__pctype_func(
   )
```

## <a name="return-value"></a>戻り値

文字分類に関する情報の配列へのポインター。

## <a name="remarks"></a>解説

文字分類テーブルに含まれる情報は内部専用であり、`char` 型の文字を分類する各種関数で使用されます。 詳細については、「[_pctype、_pwctype、_wctype、_mbctype、_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)」の「`Remarks`」セクションをご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|__pctype_func|ctype.h|

## <a name="see-also"></a>関連項目

[_pctype、_pwctype、_wctype、_mbctype、_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)
