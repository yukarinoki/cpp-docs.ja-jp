---
title: _mbsnbcpy、_mbsnbcpy_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnbcpy
- _mbsnbcpy_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsnbcpy
- _ftcsncpy
- _mbsnbcpy
- mbsnbcpy_l
- _mbsnbcpy_l
dev_langs:
- C++
helpviewer_keywords:
- mbsnbcpy function
- _mbsnbcpy_l function
- _mbsnbcpy function
- _tcsncpy function
- tcsncpy_l function
- _tcsncpy_l function
- mbsnbcpy_l function
- tcsncpy function
ms.assetid: 83d17b50-3cbf-4df9-bce8-3b6d52f85d04
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8e0972b1584f4df92455bb17e0db8e577f988ae8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213112"
---
# <a name="mbsnbcpy-mbsnbcpyl"></a>_mbsnbcpy、_mbsnbcpy_l

コピー **n**を宛先文字列に文字列のバイト。 これらの関数のセキュリティを強化したバージョンについては、「[_mbsnbcpy_s、_mbsnbcpy_s_l](mbsnbcpy-s-mbsnbcpy-s-l.md)」を参照してください。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
unsigned char * _mbsnbcpy(
   unsigned char * strDest,
   const unsigned char * strSource,
   size_t count
);
unsigned char * _mbsnbcpy_l(
   unsigned char * strDest,
   const unsigned char * strSource,
   size_t count,
   _locale_t locale
);
template <size_t size>
unsigned char * _mbsnbcpy(
   unsigned char (&strDest)[size],
   const unsigned char * strSource,
   size_t count
); // C++ only
template <size_t size>
unsigned char * _mbsnbcpy_l(
   unsigned char (&strDest)[size],
   const unsigned char * strSource,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*strDest*<br/>
文字列のコピー先。

*strSource*<br/>
コピーする文字列。

*count*<br/>
コピー対象のバイト数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbsnbcpy**コピー先文字列へのポインターを返します。 エラーを示す戻り値は予約されていません。

## <a name="remarks"></a>Remarks

**_Mbsnbcpy**関数コピー*数*からバイト*strSource*に*追加される文字*。 場合*数*のサイズを超える*追加される文字*元とコピー先の文字列が重なり合うの動作または **_mbsnbcpy**が定義されていません。

場合*strSource*または*追加される文字*null ポインターの場合は、」の説明に従って、この関数は無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 かどうかは、引き続き実行が許可された、関数を返します**NULL**設定と**errno**に**EINVAL**します。

出力値の設定に影響は、 **LC_CTYPE**ロケールのカテゴリの設定; を参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)詳細についてはします。 これらの関数バージョンが同じでないそのものを除く、 **_l**サフィックスを使用して、現在のロケールとが付いているバージョン、 **_l**サフィックスが代わりにロケール パラメーターを使用しての渡されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

> [!IMPORTANT]
> これらの関数は、バッファー オーバーランの脅威に対して脆弱な場合があります。 バッファー オーバーランを使用すると任意の攻撃者のコードを実行できるため、認められていない特権の昇格が発生し、システムを危険にさらすことがあります。 詳しくは、「 [バッファー オーバーランの回避](/windows/desktop/SecBP/avoiding-buffer-overruns)」をご覧ください。

C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティを強化された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncpy**|[strncpy](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)|**_mbsnbcpy**|[wcsncpy](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)|
|**_tcsncpy_l**|**_strncpy_l**|**_mbsnbcp_l**|**_wcsncpy_l**|

## <a name="requirements"></a>要件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_mbsnbcpy**|\<mbstring.h>|
|**_mbsnbcpy_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat、_mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp、_mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt、_wcsncnt、_mbsnbcnt、_mbsnbcnt_l、_mbsnccnt、_mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbset、_mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
