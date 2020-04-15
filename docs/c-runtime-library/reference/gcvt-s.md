---
title: _gcvt_s
ms.date: 4/2/2020
api_name:
- _gcvt_s
- _o__gcvt_s
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _gcvt_s
- gcvt_s
helpviewer_keywords:
- _gcvt_s function
- _CVTBUFSIZE
- floating-point functions, converting number to string
- gcvt_s function
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
ms.openlocfilehash: 10d2b9af45b78a3f5ed673bde3d37894ccb00168
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345369"
---
# <a name="_gcvt_s"></a>_gcvt_s

浮動小数点値を文字列に変換します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_gcvt](gcvt.md) です。

## <a name="syntax"></a>構文

```C
errno_t _gcvt_s(
   char *buffer,
   size_t sizeInBytes,
   double value,
   int digits
);
template <size_t cchStr>
errno_t _gcvt_s(
   char (&buffer)[cchStr],
   double value,
   int digits
); // C++ only
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
変換の結果を格納するバッファー。

*sizeInBytes*<br/>
バッファーのサイズ。

*value*<br/>
変換する値。

*数値*<br/>
格納されている有効桁数。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。 無効なパラメーターのためにエラーが発生した場合 (無効な値については次の表を参照)、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明するように、無効なパラメーター ハンドラーが呼び出されます。 実行を継続できる場合は、エラー コードが返されます。 エラー コードは、Errno.h で定義されています。 これらのエラーの一覧については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

### <a name="error-conditions"></a>エラー条件

|*バッファー*|*sizeInBytes*|*value*|*数値*|戻り値|*バッファ*内の値|
|--------------|-------------------|-------------|--------------|------------|-----------------------|
|**NULL**|any|any|any|**Einval**|変更されません。|
|**NULL**でない (有効なメモリを指す)|ゼロ|any|any|**Einval**|変更されません。|
|**NULL**でない (有効なメモリを指す)|any|any|>= *サイズ単位バイト数*|**Einval**|変更されません。|

**セキュリティの問題**

**バッファ**が有効なメモリを指さない場合 *、_gcvt_s*はアクセス違反を生成し **、NULL**でない場合があります。

## <a name="remarks"></a>解説

**_gcvt_s**関数は、浮動小数点*値*を文字列 (小数点と可能な符号バイトを含む) に変換し、その文字列を*buffer*に格納します。 *buffer*は、変換された値に、自動的に追加される終端の NULL 文字を収容するのに十分な大きさでなければなりません。 長さ **_CVTBUFSIZE**のバッファーは、浮動小数点値に対して十分です。 バッファ サイズが *+* 1 の場合、関数はバッファの終端を上書きしませんので、この操作に十分なバッファを用意してください。 **_gcvt_s**は、10 進形式の*数字*を生成しようとします。 できない場合は、指数形式で*数字*を生成します。 後続のゼロは、変換時に非表示にできます。

C++ では、テンプレートのオーバーロードによってこの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

この関数のデバッグ バージョンは、まず 0xFE でバッファーを埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md) を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_gcvt_s**|\<stdlib.h>|\<error.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_gcvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main()
{
    char buf[_CVTBUFSIZE];
    int decimal;
    int sign;
    int err;

    err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);

    if (err != 0)
    {
        printf("_gcvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 1.2
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt_s](ecvt-s.md)<br/>
[_fcvt_s](fcvt-s.md)<br/>
[_gcvt](gcvt.md)<br/>
