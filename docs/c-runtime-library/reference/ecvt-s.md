---
title: _ecvt_s | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ecvt_s
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
- ecvt_s
- _ecvt_s
dev_langs:
- C++
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 623d12bb515794a1d57b5a18e0e93e70d50a6812
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="ecvts"></a>_ecvt_s

変換、**二重**数値を文字列にします。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_ecvt](ecvt.md) です。

## <a name="syntax"></a>構文

```C
errno_t _ecvt_s(
   char * _Buffer,
   size_t _SizeInBytes,
   double _Value,
   int _Count,
   int *_Dec,
   int *_Sign
);
template <size_t size>
errno_t _ecvt_s(
   char (&_Buffer)[size],
   double _Value,
   int _Count,
   int *_Dec,
   int *_Sign
); // C++ only
```

### <a name="parameters"></a>パラメーター

*_Buffer*<br/>
変換の結果である数字の文字列へのポインターが格納されます。

*_SizeInBytes*<br/>
バッファーのサイズ (バイト単位)。

*_Value*<br/>
変換される数値。

*_Count*<br/>
格納する桁数。

*_Dec*<br/>
格納された小数点位置。

*_Sign*<br/>
変換後の数値の符号。

## <a name="return-value"></a>戻り値

正常終了した場合は 0。 障害が発生した場合、戻り値はエラー コードを示します。 エラー コードは、Errno.h で定義されています。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

パラメーターが次の表の無効な値の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**し、返します**EINVAL**です。

### <a name="error-conditions"></a>エラー条件

|*_Buffer*|*_SizeInBytes*|_Value|_Count|_Dec|_Sign|戻り値|値で*バッファー*|
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|
|**NULL**|任意|任意|任意|任意|任意|**EINVAL**|変更されません。|
|いない**NULL** (有効なメモリが指す)|<=0|任意|任意|任意|任意|**EINVAL**|変更されません。|
|任意|任意|任意|任意|**NULL**|任意|**EINVAL**|変更されません。|
|任意|任意|任意|任意|任意|**NULL**|**EINVAL**|変更されません。|

## <a name="security-issues"></a>セキュリティ上の問題

**_ecvt_s**場合、アクセス違反を生成する可能性があります*バッファー*が有効なメモリを指していませんありいない**NULL**です。

## <a name="remarks"></a>コメント

**_Ecvt_s**関数が文字の文字列に浮動小数点数値を変換します。 *_Value*パラメーターは変換する浮動小数点数。 この関数は最大格納*カウント*の桁 *_Value*を文字列として null 文字 ('\0') を追加するとします。 場合の桁数 *_Value*を超える *_Count*下位の桁は丸められます。 も少ない場合*カウント*数字、文字列はゼロで埋められます。

文字列には数字だけが格納されます。 小数点の記号の位置 *_Value*から取得できる *_Dec*と *_Sign*呼び出しの後です。 *_Dec*パラメーターは、文字列の先頭に対する、小数点の位置を示す整数値を指します。 0 または負の整数値は、最初の桁の左側に小数点があることを示します。 *_Sign*パラメーターを変換後の数値の符号を示す整数をポイントします。 整数値が 0 の場合、数値は正の値です。 それ以外の場合、数値は負の値です。

長さのバッファー **_CVTBUFSIZE**任意の浮動小数点値だけで十分です。

違い **_ecvt_s**と **_fcvt_s**の解釈時に、 *_Count*パラメーター。 **_ecvt_s**解釈 *_Count*として出力文字列に数字の合計数が **_fcvt_s**解釈 *_Count*後に数字の数として10 進数の点。

C++ では、テンプレートのオーバーロードによってこの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

この関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).を使用します。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|オプション ヘッダー|
|--------------|---------------------|---------------------|
|**_ecvt_s**|\<stdlib.h>|\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// ecvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( )
{
    char * buf = 0;
    int decimal;
    int sign;
    int err;

    buf = (char*) malloc(_CVTBUFSIZE);
    err = _ecvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);

    if (err != 0)
    {
        printf("_ecvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 12000
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt_s](fcvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
