---
title: _gcvt_s | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _gcvt_s
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
- _gcvt_s
- gcvt_s
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a2bd12a63db064bca0c880484f99a2df9d210f8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="gcvts"></a>_gcvt_s

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

*値*<br/>
変換する値。

*digits*<br/>
格納される有効桁数。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。 無効なパラメーターのためにエラーが発生した場合 (無効な値については次の表を参照)、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明するように、無効なパラメーター ハンドラーが呼び出されます。 実行を継続できる場合は、エラー コードが返されます。 エラー コードは、Errno.h で定義されています。 これらのエラーの一覧については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

### <a name="error-conditions"></a>エラー条件

|*バッファー*|*sizeInBytes*|*値*|*digits*|Return|値で*バッファー*|
|--------------|-------------------|-------------|--------------|------------|-----------------------|
|**NULL**|任意|任意|任意|**EINVAL**|変更されません。|
|いない**NULL** (有効なメモリが指す)|ゼロ|任意|任意|**EINVAL**|変更されません。|
|いない**NULL** (有効なメモリが指す)|任意|任意|>= *sizeInBytes*|**EINVAL**|変更されません。|

**セキュリティ上の問題**

**_gcvt_s**場合、アクセス違反を生成できます*バッファー*が有効なメモリを指していませんありいない**NULL**です。

## <a name="remarks"></a>コメント

**_Gcvt_s**関数は、浮動小数点に変換*値*を文字の文字列 (を小数点、符号バイトを含む) 内の文字列を格納および*バッファー*. *バッファー*に変換された値と自動的に追加される終端の null 文字を対応するのに十分な大きさにする必要があります。 長さのバッファー **_CVTBUFSIZE**が十分で、浮動小数点値。 場合のバッファー サイズ*桁*+ 1 が使用される、関数は、末尾を上書きしないバッファーのので、必ずこの操作のための十分なバッファーを指定します。 **_gcvt_s**生成しようとしています。*桁*10 進形式の数字です。 生成できない場合は、*桁*指数書式の数字です。 後続のゼロは、変換時に非表示にできます。

C++ では、テンプレートのオーバーロードによってこの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

この関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).を使用します。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_gcvt_s**|\<stdlib.h>|\<error.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
