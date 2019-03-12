---
title: __pctype_func
ms.date: 11/04/2016
apiname:
- __pctype_func
apilocation:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- __pctype_func
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
ms.openlocfilehash: a152f3612373189c964aaca005fe3b989eec8694
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742026"
---
# <a name="pctypefunc"></a>__pctype_func

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

## <a name="requirements"></a>要件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|__pctype_func|ctype.h|

## <a name="see-also"></a>関連項目

[_pctype、_pwctype、_wctype、_mbctype、_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)
