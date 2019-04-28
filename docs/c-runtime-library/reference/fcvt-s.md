---
title: _fcvt_s
ms.date: 04/05/2018
apiname:
- _fcvt_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fcvt_s
- _fcvt_s
helpviewer_keywords:
- fcvt_s function
- converting floating point, to strings
- floating-point functions, converting number to string
- _fcvt_s function
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
ms.openlocfilehash: 51ff3c675f1f53aee9beab629b17193164a2e7eb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334867"
---
# <a name="fcvts"></a>_fcvt_s

浮動小数点数を文字列に変換します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_fcvt](fcvt.md) です。

## <a name="syntax"></a>構文

```C
errno_t _fcvt_s(
   char* buffer,
   size_t sizeInBytes,
   double value,
   int count,
   int *dec,
   int *sign
);
template <size_t size>
errno_t _fcvt_s(
   char (&buffer)[size],
   double value,
   int count,
   int *dec,
   int *sign
); // C++ only
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
変換の結果を保持する指定されたバッファー。

*sizeInBytes*<br/>
バッファーのサイズ (バイト単位)。

*value*<br/>
変換される数値。

*count*<br/>
小数点以下の桁数。

*dec*<br/>
格納された小数点位置を指すポインター。

*sign*<br/>
格納された符号インジケーターを指すポインター。

## <a name="return-value"></a>戻り値

正常終了した場合は 0。 障害が発生した場合、戻り値はエラー コードを示します。 エラー コードは、Errno.h で定義されています。 これらのエラーの一覧については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

パラメーターが次の表の無効な値の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**返します**EINVAL**します。

### <a name="error-conditions"></a>エラー条件

|*バッファー*|*sizeInBytes*|値|count|dec|sign|Return|値*バッファー*|
|--------------|-------------------|-----------|-----------|---------|----------|------------|-----------------------|
|**NULL**|任意|任意|任意|任意|任意|**EINVAL**|変更されません。|
|いない**NULL** (有効なメモリを指す)|<=0|任意|任意|任意|任意|**EINVAL**|変更されません。|
|任意|任意|任意|任意|**NULL**|任意|**EINVAL**|変更されません。|
|任意|任意|任意|任意|任意|**NULL**|**EINVAL**|変更されません。|

## <a name="security-issues"></a>セキュリティ上の問題

**_fcvt_s**場合、アクセス違反を生成する可能性があります*バッファー*が有効なメモリを指していないとが**NULL**します。

## <a name="remarks"></a>Remarks

**_Fcvt_s**関数は、浮動小数点数を文字の null で終わる文字列に変換します。 *値*パラメーターは変換する浮動小数点数です。 **_fcvt_s**の桁を格納*値*を文字列として null 文字 ('\0') を追加します。 *カウント*パラメーターは、小数点より後に格納される桁数を指定します。 余分な桁は丸め*カウント*を配置します。 も少なかった場合*カウント*桁の文字列、有効桁数が 0 で埋められます。

文字列には数字だけが格納されます。 符号、小数点の位置*値*から取得できます*dec*と*サインオン*呼び出しの後にします。 *Dec*パラメーターが指す整数値です。 この整数値では、文字列の先頭に対する小数点の位置。 0 または負の整数値は、小数点が文字列の先頭より左にあることを示します。 パラメーター*サインオン*の符号を示す整数を指す*値*します。 場合、整数は 0 に設定されて*値*が正の値および数値の場合は 0 以外の値に設定されている*値*が負の値。

長さのバッファー **_CVTBUFSIZE**がにとって十分で、任意の浮動小数点値。

間の差 **_ecvt_s**と **_fcvt_s**の解釈には、*カウント*パラメーター。 **_ecvt_s**解釈*カウント*として、出力文字列に数字の合計数と **_fcvt_s**解釈*カウント*の後の桁数として、小数点 10 進数。

C++ では、テンプレートのオーバーロードによってこの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

この関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).を使用します。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|オプション ヘッダー|
|--------------|---------------------|---------------------|
|**_fcvt_s**|\<stdlib.h>|\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

**ライブラリ:** すべてのバージョン、 [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)します。

## <a name="example"></a>例

```C
// fcvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main()
{
    char * buf = 0;
    int decimal;
    int sign;
    int err;

    buf = (char*) malloc(_CVTBUFSIZE);
    err = _fcvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);

    if (err != 0)
    {
        printf("_fcvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 120000
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt_s](ecvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
[_fcvt](fcvt.md)<br/>
