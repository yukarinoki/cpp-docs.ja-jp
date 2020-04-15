---
title: ungetc、ungetwc
ms.date: 4/2/2020
api_name:
- ungetwc
- ungetc
- _o_ungetc
- _o_ungetwc
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
- _ungettc
- ungetwc
- ungetc
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
ms.openlocfilehash: 484af7b72f860a8a9d12cf0b62444871caad4675
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361297"
---
# <a name="ungetc-ungetwc"></a>ungetc、ungetwc

ストリームに文字をプッシュ バックします。

## <a name="syntax"></a>構文

```C
int ungetc(
   int c,
   FILE *stream
);
wint_t ungetwc(
   wint_t c,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*C*<br/>
プッシュする文字。

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

成功した場合、これらの関数は、文字引数*c*を返します。 *c を*押し戻すことができない場合、または文字が読み取られていない場合、入力ストリームは変更されず **、unetc**は**EOF**を返します。**ウンゲトウは** **WEOF**を返します。 *stream*が**NULL**の場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行が続行できる場合 **、EOF**または**WEOF**が返され **、errno**が**EINVAL**に設定されます。

これらと他のエラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**ungetc**関数は、文字*c*を*ストリーム*にプッシュし、ファイルの終わりインジケーターをクリアします。 ストリームは、読み取り用に開かれている必要があります。 *ストリーム*での後続の読み取り操作は*c*で開始されます。 **ungetc**を使用して**EOF**をストリームにプッシュしようとしても無視されます。

**ストリーム**に配置された文字が、ストリームから読み取られる前に**fflush** [、fseek](fseek-fseeki64.md) **、fsetpos**、または[rewind](rewind.md)が呼び出されると、消去されます。 ファイル位置インジケーターの値は、文字がプッシュ バックされる前のファイル位置インジケーターの値になります。 ストリームに対応する外部のストレージは変更されません。 テキスト ストリームに対する呼び出し**が成功すると**、プッシュバックされた文字がすべて読み取られるか破棄されるまで、ファイル位置インジケーターは指定されません。 バイナリストリームに対する**成功した各 ungetc**呼び出しでは、ファイル位置標識はデクリメントされます。呼び出しの前に値が 0 であった場合、その値は呼び出し後に未定義です。

2 つの呼び出しの間に読み取りまたはファイル位置決め操作を行わずに **、ungetc**が 2 回呼び出されると、結果は予測できません。 **fscanf**への呼び出しの後で **、getc**などの別の読み取り操作が実行されない限り **、ungetc**への呼び出しが失敗することがあります。 **fscanf**自体が**ungetc**を呼び出すからです。

**ungetwc**は、**ウンゲッチ**のワイド文字バージョンです。 ただし、テキストまたはバイナリー・ストリームに対して成功した**ungetwc**呼び出しのたびに、プッシュバックされた文字がすべて読み取られるか破棄されるまで、ファイル位置標識の値は指定されません。

これらの関数はスレッド セーフであり、実行時に重要情報をロックします。 ロックしないバージョンについては、「[_ungetc_nolock、_ungetwc_nolock](ungetc-nolock-ungetwc-nolock.md)」をご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**ungetc**|**ungetc**|**ungetwc**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**ungetc**|\<stdio.h>|
|**ungetwc**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールはサポートされていません。 コンソール **、stdin 、stdout**、および**stdout****stderr**に関連付けられている標準ストリーム ハンドルは、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_ungetc.c
// This program first converts a character
// representation of an unsigned integer to an integer. If
// the program encounters a character that is not a digit,
// the program uses ungetc to replace it in the  stream.
//

#include <stdio.h>
#include <ctype.h>

int main( void )
{
   int ch;
   int result = 0;

   // Read in and convert number:
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )
      result = result * 10 + ch - '0';    // Use digit.
   if( ch != EOF )
      ungetc( ch, stdin );                // Put nondigit back.
   printf( "Number = %d\nNext character in stream = '%c'",
            result, getchar() );
}
```

```Output

      521aNumber = 521
Next character in stream = 'a'
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[getc、getwc](getc-getwc.md)<br/>
[putc、putwc](putc-putwc.md)<br/>
