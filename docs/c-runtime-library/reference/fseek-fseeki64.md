---
title: fseek、_fseeki64
ms.date: 4/2/2020
api_name:
- _fseeki64
- fseek
- _o__fseeki64
- _o_fseek
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
- fseek
- _fseeki64
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
ms.openlocfilehash: e8f6021a0b770f6b435653c190d5968f9ac50a57
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345764"
---
# <a name="fseek-_fseeki64"></a>fseek、_fseeki64

指定した場所にファイル ポインターを移動します。

## <a name="syntax"></a>構文

```C
int fseek(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
**FILE** 構造体へのポインター。

*offset*<br/>
*配信元*からのバイト数。

*起源*<br/>
最初の位置。

## <a name="return-value"></a>戻り値

成功した場合 **、fseek**と **_fseeki64**は 0 を返します。 それ以外の場合は、0 以外の値を返します。 シーク非対応のデバイスでは、戻り値は未定義です。 *stream*が null ポインターの場合、または*origin*が以下で説明する許可値の 1 つでない場合は **、fseek**と **_fseeki64**が無効なパラメーター ハンドラーを呼び[出します](../../c-runtime-library/parameter-validation.md)。 実行を続行できる場合、これらの関数は**errno**を**EINVAL**に設定し、-1 を返します。

## <a name="remarks"></a>解説

**fseek**関数と **_fseeki64**関数は、*ストリーム*に関連付けられているファイル ポインタ (存在する場合) を *、起点*からの*オフセット*バイトの新しい位置に移動します。 ストリームの次の操作は、新しい場所で行われます。 更新用に開かれているストリームでの次の操作は読み取りまたは書き込みのいずれかです。 引数*の起点*は、STDIO で定義されている次のいずれかの定数でなければなりません。H：

|起点値|意味|
|-|-|
| **SEEK_CUR** | ファイル ポインターの現在の位置。 |
| **SEEK_END** | EOF (ファイル終端)。 |
| **SEEK_SET** | ファイルの先頭。 |

**fseek**と **_fseeki64**を使用すると、ファイル内の任意の場所でポインターを再配置できます。 ポインターは、ファイルの末尾を越えて配置することもできます。 **fseek**と **_fseeki64**はファイルの終わりインジケーターをクリアし、 *stream*に対する以前の[ungetc](ungetc-ungetwc.md)呼び出しの効果を否定します。

データを追加するためにファイルを開く場合、現在のファイルの位置は、次の書き込みが発生する場所ではなく最後の I/O 操作によって決まります。 追加のために開かれたファイルで I/O 操作がまだ発生していない場合、ファイルの位置はファイルの先頭です。

テキスト モードで開かれたストリームの場合、復帰改行の変換によって fseek が発生し、**予期**しない結果が_fseeki64されるため **、fseek**と**fseek****_fseeki64**の使用は制限されます。 テキスト モードで開かれたストリームで動作することが保証されている**fseek**および **_fseeki64**操作は、次の場合のみです。

- 元の値のいずれかに対して相対的なオフセット 0 でシークします。

- **fseek**を使用する場合は[ftell](ftell-ftelli64.md)の呼び出しから戻されるオフセット値を持つファイルの先頭からシークし **、_fseeki64**を使用する場合[は_ftelli64。](ftell-ftelli64.md)

テキスト モードでも、Ctrl + Z は入力時に EOF (EOF: end-of-file) 文字として解釈されます。 読み取り/書き込み用に開かれたファイルでは[、fopen](fopen-wfopen.md)と関連するすべてのルーチンがファイルの末尾に Ctrl + Z があるかどうかをチェックし、可能であれば削除します。 これは **、fseek**と[ftell](ftell-ftelli64.md)**または**_fseeki64 と[_ftelli64](ftell-ftelli64.md)の組み合わせを使用して、Ctrl + Z で終わるファイル内を移動すると **、fseek**または **_fseeki64**がファイルの末尾付近で不適切に動作する可能性があるためです。

バイト オーダー マーク (BOM) で始まるファイルを CRT で開くときには、ファイル ポインターは BOM の後ろ (つまり、ファイルの実際のコンテンツの開始位置) に配置されます。 ファイルの先頭に**fseek**する必要がある場合は[、ftell](ftell-ftelli64.md)を使用して初期位置を取得し、fseek を使用して 0 を位置に入れるのではなく、ファイルに対して**fseek**を指定します。

この関数では、実行中に他のスレッドをロックするので、スレッド セーフです。 ロックしないバージョンについては、「[_fseek_nolock、_fseeki64_nolock](fseek-nolock-fseeki64-nolock.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**fseek**|\<stdio.h>|
|**_fseeki64**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fseek.c
// This program opens the file FSEEK.OUT and
// moves the pointer to the file's beginning.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char line[81];
   int  result;

   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )
   {
      printf( "The file fseek.out was not opened\n" );
      return -1;
   }
   fprintf( stream, "The fseek begins here: "
                    "This is the file 'fseek.out'.\n" );
   result = fseek( stream, 23L, SEEK_SET);
   if( result )
      perror( "Fseek failed" );
   else
   {
      printf( "File pointer is set to middle of first line.\n" );
      fgets( line, 80, stream );
      printf( "%s", line );
    }
   fclose( stream );
}
```

```Output
File pointer is set to middle of first line.
This is the file 'fseek.out'.
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[ftell、_ftelli64](ftell-ftelli64.md)<br/>
[_lseek、_lseeki64](lseek-lseeki64.md)<br/>
[巻き戻し](rewind.md)<br/>
