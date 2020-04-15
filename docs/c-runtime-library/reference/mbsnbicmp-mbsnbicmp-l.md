---
title: _mbsnbicmp、_mbsnbicmp_l
ms.date: 4/2/2020
api_name:
- _mbsnbicmp_l
- _mbsnbicmp
- _o__mbsnbicmp
- _o__mbsnbicmp_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _mbsnbicmp_l
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
ms.openlocfilehash: 80d2708396cdaeb86c25932c3d13129fb318719a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340571"
---
# <a name="_mbsnbicmp-_mbsnbicmp_l"></a>_mbsnbicmp、_mbsnbicmp_l

2 つのマルチバイト文字ストリングの**n**バイトを比較し、大文字小文字を無視します。

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

*文字列 1*,*文字列2*<br/>
Null で終わる比較対象の文字列。

*count*<br/>
比較するバイト数。

## <a name="return-value"></a>戻り値

戻り値は、部分文字列間の関係を示しています。

|戻り値|説明|
|------------------|-----------------|
|< 0|*文字列 1*の部分文字列が*文字列 2*のサブ文字列より小さい。|
|0|*string2*サブストリングと同一の*ストリング*1 サブストリング。|
|> 0|*string1*サブストリングが*string2*より大きい。|

エラーが発生すると **、_mbsnbicmp**は String.h および Mbstring.h で定義されている **_NLSCMPERROR**を返します。

## <a name="remarks"></a>解説

**_mbsnbicmp**関数は *、string1*と*string2*の最初の*カウント*バイトの序数比較を実行します。 比較は、各文字を小文字に変換することによって実行されます。[_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md)は **、_mbsnbicmp**の大文字と小文字を区別するバージョンです。 *カウント*文字が比較される前に、いずれかの文字列で終端の NULL 文字に達すると、比較は終了します。 *カウント*文字を比較する前に、いずれかの文字列で終端の NULL 文字に達したときに文字列が等しい場合は、短い文字列が小さくなります。

**_mbsnbicmp**は[_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md)に似ていますが、文字列を文字数ではなく*カウント*バイトまで比較する点が異なります。

ASCII の表の 'Z' と 'a' の間にある文字 ('['、'\\'、']'、'^'、'_'、'\`') を含む 2 つの文字列は、場合に応じて異なる方法で比較します。 たとえば、2 つの文字列 "ABCDE" と "ABCD^" は、比較が小文字 ("abcde" > "abcd^") の場合は一方の方法を比較し、大文字の場合は他の方法 ("ABCDE" < "ABCD^") を比較します。

**_mbsnbicmp**は、現在使用されているマルチ[バイトコードページ](../../c-runtime-library/code-pages.md)に従ってマルチバイト文字シーケンスを認識します。 これは、現在のロケール設定の影響を受けません。

*string1*または*string2*のいずれかが null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように **、_mbsnbicmp**無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、関数は **_NLSCMPERROR**を返し **、errno**を**EINVAL**に設定します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsnicmp_l**|**_strnicmp_l**|**_mbsnbicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mbsnbicmp**|\<mbstring.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

「[_mbsnbcmp、_mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat、_mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp、_mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
