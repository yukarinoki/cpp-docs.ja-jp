---
title: ':::no-loc(strtol):::, :::no-loc(wcstol):::, :::no-loc(_strtol_l):::, :::no-loc(_wcstol_l):::'
ms.date: 4/2/2020
api_name:
- ':::no-loc(strtol):::'
- ':::no-loc(wcstol):::'
- ':::no-loc(_strtol_l):::'
- ':::no-loc(_wcstol_l):::'
- '_o_:::no-loc(_strtol_l):::'
- '_o_:::no-loc(_wcstol_l):::'
- '_o_:::no-loc(strtol):::'
- '_o_:::no-loc(wcstol):::'
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ':::no-loc(_wcstol_l):::'
- ':::no-loc(strtol):::'
- ':::no-loc(_tcstol):::'
- ':::no-loc(wcstol):::'
- ':::no-loc(_strtol_l):::'
- ':::no-loc(_tcstol_l):::'
helpviewer_keywords:
- ':::no-loc(wcstol)::: function'
- :::no-loc(wcstol):::_l function
- ':::no-loc(_tcstol)::: function'
- string conversion, to integers
- tcstol function
- :::no-loc(strtol):::_l function
- ':::no-loc(_wcstol_l)::: function'
- ':::no-loc(_strtol_l)::: function'
- ':::no-loc(strtol)::: function'
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
no-loc:
- ':::no-loc(strtol):::'
- ':::no-loc(wcstol):::'
- ':::no-loc(_strtol_l):::'
- ':::no-loc(_wcstol_l):::'
- ':::no-loc(LONG_MAX):::'
- ':::no-loc(LONG_MIN):::'
- ':::no-loc(errno):::'
- ':::no-loc(ERANGE):::'
- ':::no-loc(EINVAL):::'
- ':::no-loc(LC_NUMERIC):::'
- ':::no-loc(_tcstol):::'
- ':::no-loc(_tcstol_l):::'
- ':::no-loc(localeconv):::'
- ':::no-loc(setlocale):::'
- ':::no-loc(_wsetlocale):::'
- ':::no-loc(strtod):::'
- ':::no-loc(_strtod_l):::'
- ':::no-loc(wcstod):::'
- ':::no-loc(_wcstod_l):::'
- ':::no-loc(strtoll):::'
- ':::no-loc(_strtoll_l):::'
- ':::no-loc(wcstoll):::'
- ':::no-loc(_wcstoll_l):::'
- ':::no-loc(strtoul):::'
- ':::no-loc(_strtoul_l):::'
- ':::no-loc(wcstoul):::'
- ':::no-loc(_wcstoul_l):::'
- ':::no-loc(atof):::'
- ':::no-loc(_atof_l):::'
- ':::no-loc(_wtof):::'
- ':::no-loc(_wtof_l):::'
ms.openlocfilehash: a5265b434f14f299532d6f5ebb65c83d75ea63ca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232405"
---
# <a name="no-locstrtol-no-locwcstol-no-loc_strtol_l-no-loc_wcstol_l"></a>:::no-loc(strtol):::, :::no-loc(wcstol):::, :::no-loc(_strtol_l):::, :::no-loc(_wcstol_l):::

文字列を **`long`** 整数値に変換します。

## <a name="syntax"></a>構文

```C
long :::no-loc(strtol):::(
   const char *string,
   char **end_ptr,
   int base
);
long :::no-loc(wcstol):::(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base
);
long :::no-loc(_strtol_l):::(
   const char *string,
   char **end_ptr,
   int base,
   _locale_t locale
);
long :::no-loc(_wcstol_l):::(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*文字列*\
NULL で終わる変換対象の文字列。

*end_ptr*\
出力パラメーター。最後に解釈された文字の後の文字を指すように設定されます。 **NULL**の場合は無視されます。

*常用*\
使用する基数。

*国*\
使用するロケール。

## <a name="return-value"></a>戻り値

**:::no-loc(strtol):::**、 **:::no-loc(wcstol):::** 、 **:::no-loc(_strtol_l):::** 、およびは、 **:::no-loc(_wcstol_l):::** *文字列*で表される値を返します。 変換できない場合は0を返します。 この表現でオーバーフローが発生すると、 **:::no-loc(LONG_MAX):::** またはが返さ **:::no-loc(LONG_MIN):::** れます。

**:::no-loc(errno):::****:::no-loc(ERANGE):::** オーバーフローまたはアンダーフローが発生した場合、はに設定されます。 **:::no-loc(EINVAL):::** *String*が**NULL**の場合はに設定されます。 または、 *base*が0以外で、2より小さいか、または36より大きい場合。 **:::no-loc(ERANGE):::**、、 **:::no-loc(EINVAL):::** およびその他のリターンコードの詳細については、「 [_dos :::no-loc(errno)::: 、 :::no-loc(errno)::: 、_sys_errlist、および _sys_nerr](../../c-runtime-library/:::no-loc(errno):::-dos:::no-loc(errno):::-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

、、、およびの各関数は、 **:::no-loc(strtol):::** **:::no-loc(wcstol):::** **:::no-loc(_strtol_l):::** **:::no-loc(_wcstol_l):::** *文字列*をに変換し **`long`** ます。 これらは、数値の一部として認識されない最初の文字の*文字列*の読み取りを停止します。 終端の null 文字、または*基本*文字以上の最初の英数字を指定できます。

**:::no-loc(wcstol):::** と **:::no-loc(_wcstol_l):::** は、およびのワイド文字バージョンです **:::no-loc(strtol):::** **:::no-loc(_strtol_l):::** 。 *文字列*引数はワイド文字列です。 これらの関数は、と同じように動作し **:::no-loc(strtol):::** **:::no-loc(_strtol_l):::** ます。 ロケールのカテゴリの設定によって、 **:::no-loc(LC_NUMERIC):::** *文字列*の小数点文字 (小数のマーカーまたは小数点) の認識が決まります。 関数とは、 **:::no-loc(strtol):::** **:::no-loc(wcstol):::** 現在のロケールを使用します。 **:::no-loc(_strtol_l):::****:::no-loc(_wcstol_l):::** 代わりに、渡されたロケールを使用します。 詳細については、「[]」および「ロケール」を参照してください :::no-loc(setlocale)::: 。 [Locale](../../c-runtime-library/locale.md)

*End_ptr*が**NULL**の場合は無視されます。 それ以外の場合は、スキャンを停止した文字へのポインターが*end_ptr*が指す位置に格納されます。 有効な数字が見つからない場合、または無効なベースが指定されている場合は、変換できません。 *文字列*の値は、 *end_ptr*が指す位置に格納されます。

**:::no-loc(strtol):::** は、次の形式の文字列を指すこと*を想定し*ています。

> [*空白*][{ **+** &#124; **-** }] [**0** [{ **x** &#124; **x** }]] [*英数字*]

角かっこ ( `[ ]` ) は、省略可能な要素を囲みます。 中かっこと縦棒 () は、 `{ | }` 1 つの要素の代替を囲みます。 *空白*は空白文字とタブ文字で構成され、無視されます。 *英数字*は、10進数または文字の ' a ' ~ ' z ' (または ' a ' ~ ' z ') です。 このフォームに収まらない最初の文字は、スキャンを停止します。 *Base*が 2 ~ 36 の場合は、数値の基数として使用されます。 *Base*が0の場合は、文字列が指す文字列の先頭の*文字が、* ベースを決定するために使用されます。 最初の文字が0で、2番目の文字が ' x ' または ' X ' でない場合、文字列は8進数の整数として解釈されます。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。 最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。 ' A ' ~ ' z ' (または ' A ' ~ ' Z ') の文字には、10 ~ 35 の値が割り当てられます。 スキャンでは、値が*基数*より小さい文字のみが許可されます。 基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。 たとえば、*文字列*が "01" で始まるとします。 *Base*が0の場合、スキャナーはそれが8進数の整数であると想定します。 ' 8 ' または ' 9 ' の文字があると、スキャンが停止します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**:::no-loc(_tcstol):::**|**:::no-loc(strtol):::**|**:::no-loc(strtol):::**|**:::no-loc(wcstol):::**|
|**:::no-loc(_tcstol_l):::**|**:::no-loc(_strtol_l):::**|**:::no-loc(_strtol_l):::**|**:::no-loc(_wcstol_l):::**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**:::no-loc(strtol):::**|\<stdlib.h>|
|**:::no-loc(wcstol):::**|\<stdlib.h> または \<wchar.h>|
|**:::no-loc(_strtol_l):::**|\<stdlib.h>|
|**:::no-loc(_wcstol_l):::**|\<stdlib.h> または \<wchar.h>|

**:::no-loc(_strtol_l):::** 関数と **:::no-loc(_wcstol_l):::** 関数は、標準 C ライブラリの一部ではなく、Microsoft 固有のものです。 互換性の詳細については、「[互換性](../compatibility.md)」を参照してください。

## <a name="example"></a>例

の例を参照してください [:::no-loc(strtod):::](:::no-loc(strtod):::-:::no-loc(strtod):::-l-:::no-loc(wcstod):::-:::no-loc(wcstod):::-l.md) 。

## <a name="see-also"></a>関連項目

[データ変換](../data-conversion.md)\
[国](../locale.md)\
[:::no-loc(localeconv):::](:::no-loc(localeconv):::.md)\
[:::no-loc(setlocale):::, :::no-loc(_wsetlocale):::](:::no-loc(setlocale):::-w:::no-loc(setlocale):::.md)\
[文字列から数値への関数](../string-to-numeric-value-functions.md)\
[:::no-loc(strtod):::, :::no-loc(_strtod_l):::, :::no-loc(wcstod):::, :::no-loc(_wcstod_l):::](:::no-loc(strtod):::-:::no-loc(strtod):::-l-:::no-loc(wcstod):::-:::no-loc(wcstod):::-l.md)\
[:::no-loc(strtoll):::, :::no-loc(_strtoll_l):::, :::no-loc(wcstoll):::, :::no-loc(_wcstoll_l):::](:::no-loc(strtoll):::-:::no-loc(strtoll):::-l-:::no-loc(wcstoll):::-:::no-loc(wcstoll):::-l.md)\
[:::no-loc(strtoul):::, :::no-loc(_strtoul_l):::, :::no-loc(wcstoul):::, :::no-loc(_wcstoul_l):::](:::no-loc(strtoul):::-:::no-loc(strtoul):::-l-:::no-loc(wcstoul):::-:::no-loc(wcstoul):::-l.md)\
[:::no-loc(atof):::, :::no-loc(_atof_l):::, :::no-loc(_wtof):::, :::no-loc(_wtof_l):::](:::no-loc(atof):::-:::no-loc(atof):::-l-wtof-wtof-l.md)
