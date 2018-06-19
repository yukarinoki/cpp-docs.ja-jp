---
title: _mbsnbcoll、_mbsnbcoll_l、_mbsnbicoll、_mbsnbicoll_l Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnbicoll_l
- _mbsnbcoll_l
- _mbsnbcoll
- _mbsnbicoll
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
- mbsnbicoll
- mbsnbcoll
- mbsnbicoll_l
- _mbsnbcoll
- _mbsnbicoll
- _ftcsnicoll
- _ftcsncoll
- mbsnbcoll_l
dev_langs:
- C++
helpviewer_keywords:
- _mbsnbcoll_l function
- mbsnbcoll_l function
- _mbsnbcoll function
- _tcsnicoll function
- mbsnbcoll function
- mbsnbicoll_l function
- mbsnbicoll function
- _tcsncoll function
- _mbsnbicoll function
- _mbsnbicoll_l function
- tcsncoll function
- tcsnicoll function
ms.assetid: d139ed63-ccba-4458-baa2-61cbcef03e94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19e17552a674d4931134eb9d7b436a0f858843d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405394"
---
# <a name="mbsnbcoll-mbsnbcolll-mbsnbicoll-mbsnbicolll"></a>_mbsnbcoll、_mbsnbcoll_l、_mbsnbicoll、_mbsnbicoll_l

比較*n*マルチバイト コード ページ情報を使用して 2 つのマルチバイト文字列のバイト数。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _mbsnbcoll(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbcoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
int _mbsnbicoll(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbicoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*string1*、 *string2*<br/>
比較する文字列。

*count*<br/>
比較するバイト数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

戻り値の部分文字列の関係を示す*string1*と*string2*です。

|戻り値|説明|
|------------------|-----------------|
|< 0|*string1*部分文字列より小さい*string2*部分文字列。|
|0|*string1*部分文字列と同じ*string2*部分文字列。|
|> 0|*string1*部分文字列より大きい*string2*部分文字列。|

場合*string1*または*string2*は**NULL**または*カウント*がより大きい**INT_MAX**、無効なパラメーター ハンドラーが呼び出されます」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 これらの関数を返すかどうかは、引き続き実行が許可された、**すると**設定と**errno**に**EINVAL**です。 使用する**すると**、String.h または Mbstring.h です。

## <a name="remarks"></a>コメント

これらの各関数は、最長で 1 つ目*カウント*バイト*string1*と*string2*し、その結果の間の関係を示す値を返します部分文字列を*string1*と*string2*です。 場合の部分文字列の最後のバイト*string1*または*string2*先行バイトの比較には含まれません。 これらの関数は、部分文字列の完全な文字だけを比較します。 **_mbsnbicoll**は大文字と小文字のバージョンの **_mbsnbcoll**です。 同様に[_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md)と[_mbsnbicmp](mbsnbicmp-mbsnbicmp-l.md)、 **_mbsnbcoll**と **_mbsnbicoll**に従って 2 つのマルチバイト文字の文字列を照合します、マルチバイトで指定された辞書式順序[コード ページ](../../c-runtime-library/code-pages.md)現在使用中です。

一部のコード ページおよびそれに対応する文字セットでは、文字セットの文字の順序が辞書式の順序と異なる場合があります。 "C" ロケールでは、前述とは異なり、ASCII 文字セットの文字の順序が辞書式の文字の順序と同じです。 しかし、たとえば、ヨーロッパの一部のコード ページでは、文字 a (値 0x61) は文字セットで文字 'ä' (値 0xE4) の前にありますが、辞書式の順序では文字 'ä' が文字 'a' の前にあります。 このようなインスタンスにバイトを文字列の辞書式比較を実行するには使用 **_mbsnbcoll**なく **_mbsnbcmp**だけ文字列の等価性を確認して、使用する以外の場合は **_mbsnbcmp**.

**Coll**関数が辞書式比較については、文字列を照合して、 **cmp**関数が単に文字列の等価性、テスト、 **coll**関数は、対応するよりもかなり遅く**cmp**バージョン。 したがって、 **coll**関数は、文字セット順序と辞書式文字順序との間、現在のコード ページ内の相違があるし、この違いが比較に関係している場合にのみ、使用する必要があります。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 **_l** サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。**_l** サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncoll**|[_strncoll](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|**_mbsnbcoll**|[_wcsncoll](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|
|**_tcsncoll_l**|[_strncoll、_wcsncoll、_mbsncoll、_strncoll_l、_wcsncoll_l、_mbsncoll_l](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|**_mbsnbcoll_l**|[_wcsncoll_l](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|
|**_tcsnicoll**|[_strnicoll](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|**_mbsnbicoll**|[_wcsnicoll](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|
|**_tcsnicoll_l**|[_strnicoll_l](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|**_mbsnbicoll_l**|[_wcsnicoll_l](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mbsnbcoll**|\<mbstring.h>|
|**_mbsnbcoll_l**|\<mbstring.h>|
|**_mbsnbicoll**|\<mbstring.h>|
|**_mbsnbicoll_l**|\<mbstring.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat、_mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp、_mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp、_mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcoll 系関数](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
