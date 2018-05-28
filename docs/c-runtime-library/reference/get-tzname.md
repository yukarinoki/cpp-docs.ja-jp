---
title: _get_tzname | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_tzname
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_tzname
- get_tzname
dev_langs:
- C++
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4b49aa404dda6234382ae461459dece64e5996d
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
---
# <a name="gettzname"></a>_get_tzname

タイム ゾーン名または夏時間ゾーン名 (DST) の文字列表現を取得します。

## <a name="syntax"></a>構文

```C
errno_t _get_tzname(
    size_t* pReturnValue,
    char* timeZoneName,
    size_t sizeInBytes,
    int index
);
```

### <a name="parameters"></a>パラメーター

*pReturnValue*<br/>
文字列の長さ*timeZoneName* null 終端文字を含むです。

*timeZoneName*<br/>
文字列のタイム ゾーンの名前または夏時間標準タイム ゾーン名 (DST) の表現によってアドレス*インデックス*です。

*sizeInBytes*<br/>
サイズ、 *timeZoneName*文字の文字列 (バイト単位)。

*index*<br/>
取得する 2 つのタイム ゾーン名のいずれかのインデックス。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 それ以外の場合、 **errno**値を入力します。

いずれか*timeZoneName*は**NULL**、または*sizeInBytes*がゼロまたは 0 (ただし、両方は必要ありません) よりも小さい無効なパラメーター ハンドラーが呼び出される、」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**し、返します**EINVAL**です。

### <a name="error-conditions"></a>エラー条件

|*pReturnValue*|*timeZoneName*|*sizeInBytes*|*index*|戻り値|内容*timeZoneName*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|TZ 名のサイズ|**NULL**|0|0 または 1|0|変更されない|
|TZ 名のサイズ|任意|> 0|0 または 1|0|TZ 名|
|変更されない|**NULL**|> 0|任意|**EINVAL**|変更されない|
|変更されない|任意|ゼロ|任意|**EINVAL**|変更されない|
|変更されない|任意|> 0|> 1|**EINVAL**|変更されない|

## <a name="remarks"></a>コメント

**_Get_tzname**関数のアドレスにタイム ゾーンの名前または夏時間標準タイム ゾーン名 (DST) の文字の文字列表現を取得する*timeZoneName*によっては、インデックス値の文字列のサイズとともに*pReturnValue*です。 場合*timeZoneName*は**NULL**と*sizeInBytes*が 0 でゾーン (バイト単位) が返される時刻の文字列のサイズだけ*pReturnValue*. インデックス値は、標準タイム ゾーンが 0、または夏時間ゾーンが 1 のいずれかでなければなりません。他のインデックス値では結果が未確定となります。

### <a name="index-values"></a>インデックス値

|*index*|内容*timeZoneName*|*timeZoneName*既定値|
|-------------|--------------------------------|----------------------------------|
|0|タイム ゾーン名|「PST」|
|1|夏時間ゾーン名|「PDT」|
|> 1 または < 0|**errno** 'éý' **EINVAL**|変更されない|

実行時に値を明示的に変更しない限り、既定値はそれぞれ「PST」および「PDT」です。  これらの文字配列のサイズを受ける**TZNAME_MAX**値。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_get_tzname**|\<time.h>|

詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[TZNAME_MAX](../../c-runtime-library/tzname-max.md)<br/>
