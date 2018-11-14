---
title: ungetc、ungetwc
ms.date: 11/04/2016
apiname:
- ungetwc
- ungetc
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: c504540f8fbbe14961fa051bb93ebef350c2c1da
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51332388"
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

*c*<br/>
プッシュする文字。

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

成功すると、各これらの関数を返します。 文字引数*c*します。 場合*c*プッシュ バックできない文字を読まれなかった場合は、入力ストリームは変更されませんまたはと**ungetc**返します**EOF**;**ungetwc**返します**WEOF**します。 場合*ストリーム*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**EOF**または**WEOF**が返されますと**errno**に設定されている**EINVAL**します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**Ungetc**関数の文字をプッシュする*c*戻さ*ストリーム*し、ファイルの終わりインジケーターをクリアします。 ストリームは、読み取り用に開かれている必要があります。 後続の読み取り操作*ストリーム*で始まる*c*します。 プッシュしよう**EOF**を使用してストリームに**ungetc**は無視されます。

ストリームに文字**ungetc**場合が消去される**fflush**、 [fseek](fseek-fseeki64.md)、 **fsetpos**、または[を巻き戻す](rewind.md)ストリームから文字を読み取る前に呼び出されます。 ファイル位置インジケーターの値は、文字がプッシュ バックされる前のファイル位置インジケーターの値になります。 ストリームに対応する外部のストレージは変更されません。 成功**ungetc**すべてのプッシュ バックされた文字の読み取りまたは破棄されるまでは、ファイル位置インジケーター、テキスト ストリームに対する呼び出しは指定されていません。 各成功**ungetc**呼び出しに対して、バイナリ ストリーム、ファイル位置インジケーターがデクリメントされます。 その値を呼び出す前に 0 であった場合、値は未定義の呼び出しの後です。

結果は予測できない場合**ungetc**は読み取りまたは 2 つの呼び出しの間のファイル位置の操作なし 2 回呼び出されます。 呼び出しの後に**fscanf**への呼び出し**ungetc**しない限り、他の読み取り操作が失敗する可能性があります (など**getc**) が実行されています。 これは、ため**fscanf**自体を呼び出す**ungetc**します。

**ungetwc**のワイド文字バージョンは、 **ungetc**します。 各でただし、成功した**ungetwc**テキストまたはバイナリ ストリームで、ファイル位置インジケーターの値に対して呼び出しが指定されていないすべてのプッシュ バックされた文字の読み取りまたは破棄されるまで。

これらの関数はスレッド セーフであり、実行時に重要情報をロックします。 ロックしないバージョンについては、「[_ungetc_nolock、_ungetwc_nolock](ungetc-nolock-ungetwc-nolock.md)」をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**ungetc**|**ungetc**|**ungetwc**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**ungetc**|\<stdio.h>|
|**ungetwc**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールがサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル**stdin**、 **stdout**、および**stderr**、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
