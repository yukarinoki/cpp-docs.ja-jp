---
title: _mbsnbicmp、_mbsnbicmp_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnbicmp_l
- _mbsnbicmp
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
- _strnicmp
- _wcsnicmp_l
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _tcsnicmp
- _strnicmp_l
- _tcsnicmp_l
- _wcsnicmp
- _mbsnbicmp_l
dev_langs:
- C++
helpviewer_keywords:
- _tcsnicmp_l function
- _strnicmp function
- mbsnbicmp_l function
- _wcsnicmp_l function
- _mbsnbicmp function
- _mbsnbicmp_l function
- _tcsnicmp function
- _strnicmp_l function
- mbsnbicmp function
- _wcsnicmp function
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15038e42b87a9803312df79eb5d235f1add51669
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405017"
---
# <a name="mbsnbicmp-mbsnbicmpl"></a>_mbsnbicmp、_mbsnbicmp_l

比較**n** 2 つのマルチバイト文字のバイトは、文字列し、小文字を無視します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _mbsnbicmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
```

### <a name="parameters"></a>パラメーター

*string1*、 *string2*<br/>
Null で終わる比較対象の文字列。

*count*<br/>
比較するバイト数。

## <a name="return-value"></a>戻り値

戻り値は、部分文字列間の関係を示しています。

|戻り値|説明|
|------------------|-----------------|
|< 0|*string1*部分文字列より小さい*string2*部分文字列。|
|0|*string1*部分文字列と同じ*string2*部分文字列。|
|> 0|*string1*部分文字列より大きい*string2*部分文字列。|

エラーが発生した、 **_mbsnbicmp**返します**すると**、String.h および Mbstring.h で定義されています。

## <a name="remarks"></a>コメント

**_Mbsnbicmp**関数は、最大で 1 つ目の序数に基づく比較を実行*カウント*バイトの*string1*と*string2*です。 各文字を小文字; に変換することで、比較を実行します。[_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md)のバージョンが大文字小文字を区別 **_mbsnbicmp**です。 比較する前にいずれかの文字列で終端の null 文字に到達した場合の終了*カウント*文字を比較します。 文字列が等しい場合、終端の null 文字に達する前にいずれかの文字列で*カウント*文字数の比較は、短い文字列が小さくなります。

**_mbsnbicmp**に似ていますが[_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md)まで文字列を比較する点を除いて、*カウント*の代わりに文字のバイト数。

ASCII の表の 'Z' と 'a' の間にある文字 ('['、'\\'、']'、'^'、'_'、'\`') を含む 2 つの文字列は、場合に応じて異なる方法で比較します。 "ABCDE"を文字列 2 などと"ABCD ^"、比較が小文字である場合は、1 つの方法を比較 ("abcde">"abcd ^") とは別の方法 ("ABCDE"<"ABCD ^") 大文字である場合。

**_mbsnbicmp**に従ってマルチバイト文字シーケンスを認識、[マルチバイト コード ページ](../../c-runtime-library/code-pages.md)現在使用中です。 これは、現在のロケール設定の影響を受けません。

いずれか*string1*または*string2* null ポインターでは、 **_mbsnbicmp** 」の説明に従って無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md). 実行は継続許可されたかどうか、関数を返します**すると**設定と**errno**に**EINVAL**です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsnicmp_l**|**_strnicmp_l**|**_mbsnbicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mbsnbicmp**|<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[_mbsnbcmp、_mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat、_mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp、_mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
