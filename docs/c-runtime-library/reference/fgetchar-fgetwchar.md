---
title: _fgetchar、_fgetwchar
ms.date: 11/04/2016
apiname:
- _fgetchar
- _fgetwchar
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
- fgetwchar
- _fgettchar
- _fgetchar
- _fgetwchar
- fgettchar
helpviewer_keywords:
- fgetwchar function
- _fgetchar function
- fgettchar function
- _fgetwchar function
- _fgettchar function
- standard input, reading from
- fgetchar function
ms.assetid: 8bce874c-701a-41a3-b1b2-feff266fb5b9
ms.openlocfilehash: c74618fa0be5392062d13618ff73e2ef45bf7c2a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333957"
---
# <a name="fgetchar-fgetwchar"></a>_fgetchar、_fgetwchar

文字を読み取ります**stdin**します。

## <a name="syntax"></a>構文

```C
int _fgetchar( void );
wint_t _fgetwchar( void );
```

## <a name="return-value"></a>戻り値

**\_fgetchar**として読み取られた文字を返します、 **int**返しますまたは`EOF`エラーまたはファイルの終わりを示します。 **\_fgetwchar**から制御が戻るとして、 [wint_t](../../c-runtime-library/standard-types.md)、ワイド文字を読み取る文字に対応する値または`WEOF`エラーまたはファイルの終わりを示します。 両方の関数を使用して、 **feof**または**ferror**エラーと、ファイルの終わり条件とを区別します。

## <a name="remarks"></a>Remarks

これらの関数から単一の文字を読み取る**stdin**します。 関数は、次の文字 (定義されている場合) を指すように、関連ファイルのポインターをインクリメントします。 ストリームがファイルの末尾にある場合、ストリームのファイルの末尾を示すインジケーターが設定されます。

**_fgetchar**と等価`fgetc( stdin )`します。 等しくも**getchar**が、関数とマクロではなく関数としてのみを実装します。 **_fgetwchar**のワイド文字バージョンは、 **_fgetchar**します。

これらの関数は ANSI 規格と互換性がありません。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_fgettchar**|**_fgetchar**|**_fgetchar**|**_fgetwchar**|

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_fgetchar**|\<stdio.h>|
|**_fgetwchar**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールがサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル、**stdin**、 **stdout**、および**stderr**-C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fgetchar.c
// This program uses _fgetchar to read the first
// 80 input characters (or until the end of input)
// and place them into a string named buffer.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char buffer[81];
   int  i, ch;

   // Read in first 80 characters and place them in "buffer":
   ch = _fgetchar();
   for( i=0; (i < 80 ) && ( feof( stdin ) == 0 ); i++ )
   {
      buffer[i] = (char)ch;
      ch = _fgetchar();
   }

   // Add null to end string
   buffer[i] = '\0';
   printf( "%s\n", buffer );
}
```

```Output

      Line one.
Line two.Line one.
Line two.
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fputc、fputwc](fputc-fputwc.md)<br/>
[getc、getwc](getc-getwc.md)<br/>
