---
title: _get_tzname
ms.date: 4/2/2020
api_name:
- _get_tzname
- _o__get_tzname
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_tzname
- get_tzname
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
ms.openlocfilehash: 50f1f6e4320e3ef905b4eda67ba1d458a5b1df08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344871"
---
# <a name="_get_tzname"></a>_get_tzname

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

*値を返します。*<br/>
null 終端文字を含む*timeZoneName*の文字列の長さ。

*タイムゾーン名*<br/>
*index*に応じて、タイム ゾーン名または夏時間標準タイム ゾーン名 (DST) の表現に使用する文字列のアドレス。

*sizeInBytes*<br/>
*タイム ゾーン名*の文字列のサイズ (バイト単位)。

*index*<br/>
取得する 2 つのタイム ゾーン名のいずれかのインデックス。

|*index*|*タイムゾーン名*の内容|*デフォルト*値|
|-|-|-|
|0|タイム ゾーン名|「PST」|
|1|夏時間ゾーン名|「PDT」|
|> 1 または < 0|**errno**が**EINVAL**に設定されています|変更されない|

実行時に値を明示的に変更しない限り、既定値はそれぞれ「PST」および「PDT」です。

## <a name="return-value"></a>戻り値

成功した**場合は**0 を返します。

いずれかの*timeZoneName*が**NULL、** または*sizeInBytes*が 0 未満の場合 (両方ではなく) パラメーター[の検証](../../c-runtime-library/parameter-validation.md)で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、この関数は**errno**を**EINVAL**に設定し **、EINVAL**を返します。

### <a name="error-conditions"></a>エラー条件

|*値を返します。*|*タイムゾーン名*|*sizeInBytes*|*index*|戻り値|*タイムゾーン名*の内容|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|TZ 名のサイズ|**NULL**|0|0 または 1|0|変更されない|
|TZ 名のサイズ|any|> 0|0 または 1|0|TZ 名|
|変更されない|**NULL**|> 0|any|**Einval**|変更されない|
|変更されない|any|ゼロ|any|**Einval**|変更されない|
|変更されない|any|> 0|> 1|**Einval**|変更されない|

## <a name="remarks"></a>解説

**_get_tzname**関数は、現在のタイム ゾーン名または夏時間標準タイム ゾーン名 (DST) の文字列形式を、インデックス値に応じて*timeZoneName*のアドレスに取得し *、pReturnValue*内の文字列のサイズを取得します。 *タイム ゾーン名*が**NULL**で*sizeInBytes が*0 の場合、指定したタイム ゾーンを保持するために必要な文字列のサイズとバイト単位の終端 NULL が*pReturnValue*に返されます。 インデックス値は、標準タイム ゾーンの場合は 0、夏時間標準タイム ゾーンの場合は 1 のいずれかです。*インデックス*の他の値は、未確定の結果を持ちます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="example"></a>例

このサンプルでは **、_get_tzname**呼び出して、現在のデイライト標準タイム ゾーン名を表示するために必要なバッファー サイズを取得し、そのサイズのバッファーを割り当て **、_get_tznameを**再度呼び出してバッファーに名前を読み込み、コンソールに出力します。

```C
// crt_get_tzname.c
// Compile by using: cl /W4 crt_get_tzname.c
#include <stdio.h>
#include <time.h>
#include <malloc.h>

enum TZINDEX {
    STD,
    DST
};

int main()
{
    size_t tznameSize = 0;
    char * tznameBuffer = NULL;

    // Get the size of buffer required to hold DST time zone name
    if (_get_tzname(&tznameSize, NULL, 0, DST))
        return 1;    // Return an error value if it failed

    // Allocate a buffer for the name
    if (NULL == (tznameBuffer = (char *)(malloc(tznameSize))))
        return 2;    // Return an error value if it failed

    // Load the name in the buffer
    if (_get_tzname(&tznameSize, tznameBuffer, tznameSize, DST))
        return 3;    // Return an error value if it failed

    printf_s("The current Daylight standard time zone name is %s.\n", tznameBuffer);
    return 0;
}
```

### <a name="output"></a>出力

```Output
The current Daylight standard time zone name is PDT.
```

## <a name="requirements"></a>必要条件

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
