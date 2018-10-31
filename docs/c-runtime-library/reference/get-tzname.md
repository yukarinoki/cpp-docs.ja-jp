---
title: _get_tzname | Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
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
ms.openlocfilehash: d773d5d98466963ef621cc3fa7bc5ab8b4acc40a
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990309"
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
に応じて、タイム ゾーン名または夏時間標準タイム ゾーン名 (DST) の表現の文字の文字列のアドレス*インデックス*します。

*sizeInBytes*<br/>
サイズ、 *timeZoneName*文字の文字列 (バイト単位)。

*index*<br/>
取得する 2 つのタイム ゾーン名のいずれかのインデックス。

|*index*|内容*timeZoneName*|*timeZoneName*既定値|
|-|-|-|
|0|タイム ゾーン名|「PST」|
|1|夏時間ゾーン名|「PDT」|
|> 1 または < 0|**errno**設定**EINVAL**|変更されない|

実行時に値を明示的に変更しない限り、既定値はそれぞれ「PST」および「PDT」です。

## <a name="return-value"></a>戻り値

成功した場合は 0 それ以外の場合、 **errno**値を入力します。

いずれか*timeZoneName*は**NULL**、または*sizeInBytes*が 0 か、無効なパラメーター ハンドラーが呼び出される 0 個 (ただし、両方は必要ありません) より小さい」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**返します**EINVAL**します。

### <a name="error-conditions"></a>エラー条件

|*pReturnValue*|*timeZoneName*|*sizeInBytes*|*index*|戻り値|内容*timeZoneName*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|TZ 名のサイズ|**NULL**|0|0 または 1|0|変更されない|
|TZ 名のサイズ|任意|> 0|0 または 1|0|TZ 名|
|変更されない|**NULL**|> 0|任意|**EINVAL**|変更されない|
|変更されない|任意|ゼロ|任意|**EINVAL**|変更されない|
|変更されない|任意|> 0|> 1|**EINVAL**|変更されない|

## <a name="remarks"></a>Remarks

**_Get_tzname**関数のアドレスに現在のタイム ゾーン名または夏時間標準タイム ゾーン名 (DST) の文字の文字列表現を取得する*timeZoneName*に応じて、インデックス値、文字列のサイズと共に*pReturnValue*します。 場合*timeZoneName*は**NULL**と*sizeInBytes*は 0 を指定されたタイム ゾーンを保持するために必要な文字列のサイズとで(バイト単位)の終端のnullが返されます*pReturnValue*します。 いずれかの標準時ゾーンの場合は 0 または 1 標準時ゾーンの夏時間; をインデックス値がある必要があります。その他の値の*インデックス*が未確定の結果。

## <a name="example"></a>例

このサンプルを呼び出す **_get_tzname**現在夏時間標準タイム ゾーン名を表示する必要なバッファー サイズを取得するには、呼び出し、そのサイズのバッファーを割り当てます **_get_tzname**内の名前をもう一度、バッファーし、し、コンソールに出力します。

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

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_get_tzname**|\<time.h>|

詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
