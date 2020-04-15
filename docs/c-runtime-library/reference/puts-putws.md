---
title: puts、_putws
ms.date: 4/2/2020
api_name:
- _putws
- puts
- _o__putws
- _o_puts
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _putts
- _putws
- puts
helpviewer_keywords:
- strings [C++], writing
- _putts function
- standard output, writing to
- putws function
- puts function
- putts function
- _putws function
ms.assetid: 32dada12-ed45-40ac-be06-3feeced9ecd6
ms.openlocfilehash: 9681373ccf338daf05be3120fbadd39ba471e86a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332956"
---
# <a name="puts-_putws"></a>puts、_putws

**stdout** に文字列を書き込みます。

## <a name="syntax"></a>構文

```C
int puts(
   const char *str
);
int _putws(
   const wchar_t *str
);
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
出力する文字列。

## <a name="return-value"></a>戻り値

正常に終了した場合は、0 以上の値を返します。 **プット**が失敗した場合は **、EOF**を返します。**_putws**失敗した場合は **、WEOF**を返します。 *str*が null ポインターの場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、関数は**errno**を**EINVAL**に設定し **、EOF**または**WEOF**を返します。

これらと他のエラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**puts**関数は *、str*を標準出力ストリーム**stdout**に書き込み、文字列の終端の null 文字 ('\0') を出力ストリームの改行文字 ('\n') に置き換えます。

**_putws**は、**プット**のワイド文字バージョンです。この 2 つの関数は、ANSI モードでストリームが開かれた場合に同じように動作します。 **現在、プット**は UNICODE ストリームへの出力をサポートしていません。

**_putwchは**、現在のコンソール ロケール設定を使用して Unicode 文字を書き込みます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_putts**|**puts**|**puts**|**_putws**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**puts**|\<stdio.h>|
|**_putws**|\<stdio.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールはサポートされていません。 コンソール **、stdin 、stdout**、および**stdout****stderr**に関連付けられている標準ストリーム ハンドルは、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_puts.c
// This program uses puts to write a string to stdout.

#include <stdio.h>

int main( void )
{
   puts( "Hello world from puts!" );
}
```

### <a name="output"></a>出力

```Output
Hello world from puts!
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fputs、fputws](fputs-fputws.md)<br/>
[fgets、fgetws](fgets-fgetws.md)<br/>
