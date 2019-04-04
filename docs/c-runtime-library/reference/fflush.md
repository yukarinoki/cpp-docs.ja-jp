---
title: fflush
ms.date: 11/04/2016
apiname:
- fflush
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
- fflush
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
ms.openlocfilehash: d03d20ee5024915d0ca4c5a21db4159e8c4f876a
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51329112"
---
# <a name="fflush"></a>fflush

ストリームをフラッシュします。

## <a name="syntax"></a>構文

```C
int fflush(
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

**fflush**バッファーが正常にフラッシュされた場合は 0 を返します。 指定したストリームにバッファーがないか、読み取り専用で開かれる場合にも、値 0 が返されます。 戻り値**EOF**はエラーを示します。

> [!NOTE]
> 場合**fflush**返します**EOF**データが、書き込みの失敗により失われた可能性があります。 重大なエラー ハンドラーを設定する場合は、バッファリングを無効にで最も安全な**setvbuf**関数または下位入出力ルーチンを使用する**開く (_o)**、 **_close**と **_write**ストリーム I/O 関数ではなく。

## <a name="remarks"></a>Remarks

**Fflush**関数は、ストリームをフラッシュ*ストリーム*します。 書き込みモードでストリームを開いた場合、または更新モードで開き、最後の操作が書き込みだった場合、基になるファイルまたはデバイスにストリーム バッファーの内容が書き込まれ、バッファーは破棄されます。 ストリームが読み取りモードで開かれた場合、またはストリームがバッファーへの呼び出しを持たない場合**fflush**影響を与えませんし、バッファーが保持されます。 呼び出し**fflush**への以前の呼び出しの効果が無視されます**ungetc**ストリーム。 呼び出し後もストリームは開いたままになります。

場合*ストリーム*は**NULL**、動作はへの呼び出しと同じ**fflush**で開いている各ストリーム。 書き込みモードで開いたすべてのストリームと、更新モードで開いて最後の操作が書き込みだったすべてのストリームは、フラッシュされます。 この呼び出しは、他のストリームに影響がありません。

バッファーは通常はオペレーティング システムによって保持され、データをディスクに自動的に書き込むための最適なタイミングが決定されます。タイミングとしては、バッファーがいっぱいになったとき、ストリームが閉じられるとき、プログラムがストリームを閉じずに正常に終了したときがあります。 ランタイム ライブラリのディスクへのコミットの機能を使用すると、重要なデータをオペレーティング システムのバッファーではなく、ディスクに直接書き込むことができます。 プログラムのオブジェクト ファイルを COMMODE.OBJ にリンクすると、既存のプログラムを書き直さずに、この機能を有効にできます。 呼び出し、結果として得られる実行可能ファイルで **_flushall**をディスクにすべてのバッファーの内容を記述します。 のみ **_flushall**と**fflush** COMMODE.OBJ の影響を受けます。

ディスクへのコミットの機能の制御については、「[ストリーム入出力](../../c-runtime-library/stream-i-o.md)」、「[fopen](fopen-wfopen.md)」、および「[_fdopen](fdopen-wfdopen.md)」を参照してください。

この関数は呼び出し元スレッドをロックするため、スレッド セーフです。 ロックしないバージョンでは、**_fflush_nolock**を参照してください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**fflush**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fflush.c
#include <stdio.h>
#include <conio.h>

int main( void )
{
   int integer;
   char string[81];

   // Read each word as a string.
   printf( "Enter a sentence of four words with scanf: " );
   for( integer = 0; integer < 4; integer++ )
   {
      scanf_s( "%s", string, sizeof(string) );
      printf( "%s\n", string );
   }

   // You must flush the input buffer before using gets.
   // fflush on input stream is an extension to the C standard
   fflush( stdin );
   printf( "Enter the same sentence with gets: " );
   gets_s( string, sizeof(string) );
   printf( "%s\n", string );
}
```

```Input
This is a test
This is a test
```

```Output
Enter a sentence of four words with scanf: This is a test
This
is
a
test
Enter the same sentence with gets: This is a test
This is a test
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[_flushall](flushall.md)<br/>
[setvbuf](setvbuf.md)<br/>
