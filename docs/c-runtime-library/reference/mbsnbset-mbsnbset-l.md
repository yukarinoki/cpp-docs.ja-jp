---
title: _mbsnbset、_mbsnbset_l
ms.date: 4/2/2020
api_name:
- _mbsnbset
- _mbsnbset_l
- _o__mbsnbset
- _o__mbsnbset_l
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
- mbsnbset
- mbsnbset_l
- _mbsnbset
- _mbsnbset_l
helpviewer_keywords:
- tcsnset function
- _tcsnset_l function
- _mbsnbset function
- _tcsnset function
- _mbsnbset_l function
- mbsnbset_l function
- tcsnset_l function
- mbsnbset function
ms.assetid: 8e46ef75-9a56-42d2-a522-a08450c67c19
ms.openlocfilehash: 57c6d1a81c9aac817b0028e8eccad38d03b0eef7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340551"
---
# <a name="_mbsnbset-_mbsnbset_l"></a>_mbsnbset、_mbsnbset_l

マルチバイト文字ストリングの最初の**n**バイトを、指定した文字に設定します。 これらの関数にはセキュリティを強化したバージョンがあります。「[_mbsnbset_s、_mbsnbset_s_l](mbsnbset-s-mbsnbset-s-l.md)」を参照してください。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
unsigned char *_mbsnbset(
   unsigned char *str,
   unsigned int c,
   size_t count
);
unsigned char *_mbsnbset_l(
   unsigned char *str,
   unsigned int c,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
変更対象の文字列。

*C*<br/>
1 バイトまたはマルチバイト文字の設定。

*count*<br/>
設定対象のバイト数。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbsnbset**変更された文字列へのポインターを返します。

## <a name="remarks"></a>解説

**_mbsnbset**関数と **_mbsnbset_l**関数は、最大で*str*の最初の*カウント*バイトを c に設定*します*。 *count*が*str*の長さより大きい場合は *、count*の代わりに*str*の長さが使用されます。 *c*がマルチバイト文字で *、count*で指定された最後のバイトに完全に設定できない場合、最後のバイトにはブランク文字が埋め込まれます。 **_mbsnbset**と **_mbsnbset_l**は*str*の末尾に終端の null を置かない。

**_mbsnbset**と **_mbsnbset_l**は、 *c*のカウント文字ではなく*カウント*バイトを*count*設定する点を除いて **、 _mbsnset**に似ています。

*str*が**NULL**または*カウント*がゼロの場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター例外を生成します。 実行を続行できる場合 **、errno**は**EINVAL**に設定され、関数は**NULL**を返します。 また *、c*が有効なマルチバイト文字でない場合は **、errno**が**EINVAL**に設定され、代わりにスペースが使用されます。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 この関数の **_mbsnbset**バージョンでは、このロケールに依存する動作に現在のロケールが使用されます。**_mbsnbset_l**バージョンは、代わりに渡されたロケールパラメータを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

**セキュリティに関するメモ** この API は、バッファー オーバーランが原因で発生する潜在的な脅威の影響を受けます。 バッファー オーバーランは、システムを攻撃するときによく使用される方法であり、その結果、認められていない権限が昇格されます。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnset**|**_strnset**|**_mbsnbset**|**_wcsnset**|
|**_tcsnset_l**|**_strnset_l**|**_mbsnbset_l**|**_wcsnset_l**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mbsnbset**|\<mbstring.h>|
|**_mbsnbset_l**|\<mbstring.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_mbsnbset.c
// compile with: /W3
#include <mbstring.h>
#include <stdio.h>

int main( void )
{
   char string[15] = "This is a test";
   /* Set not more than 4 bytes of string to be *'s */
   printf( "Before: %s\n", string );
   _mbsnbset( string, '*', 4 ); // C4996
   // Note; _mbsnbset is deprecated; consider _mbsnbset_s
   printf( "After:  %s\n", string );
}
```

### <a name="output"></a>出力

```Output
Before: This is a test
After:  **** is a test
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat、_mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_strnset、_strnset_l、_wcsnset、_wcsnset_l、_mbsnset、_mbsnset_l](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)<br/>
[_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
