---
title: freopen、_wfreopen
ms.date: 11/04/2016
apiname:
- freopen
- _wfreopen
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
- _wfreopen
- _tfreopen
- freopen
helpviewer_keywords:
- _wfreopen function
- file pointers [C++], reassigning
- _tfreopen function
- freopen function
- tfreopen function
- wfreopen function
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
ms.openlocfilehash: 4c570837bddea1f5e986ae5f767279ab2637ea21
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332989"
---
# <a name="freopen-wfreopen"></a>freopen、_wfreopen

ファイル ポインターを再度割り当てます。 これらの関数にはセキュリティが強化されたバージョンがあります。「[freopen_s、_wfreopen_s](freopen-s-wfreopen-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
FILE *freopen(
   const char *path,
   const char *mode,
   FILE *stream
);
FILE *_wfreopen(
   const wchar_t *path,
   const wchar_t *mode,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*path*<br/>
新しいファイル パス。

*モード*<br/>
アクセス許可の種類。

*stream*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

これらの各関数は、新しく開かれたファイルへのポインターを返します。 エラーが発生した場合は、元のファイルが閉じられた関数を返します、 **NULL**ポインター値です。 場合*パス*、*モード*、または*ストリーム*が null ポインターの場合、または*ファイル名*空の文字列は、これらの関数は無効なパラメーターを呼び出しますハンドラー、」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**戻って**NULL**します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

これらの関数にはセキュリティが強化されたバージョンがあります。「[freopen_s、_wfreopen_s](freopen-s-wfreopen-s.md)」を参照してください。

**Freopen**関数に関連付けられているファイルを閉じます*ストリーム*し、再割り当て*ストリーム*によって指定されたファイルに*パス*します。 **_wfreopen**のワイド文字バージョンは、 **_freopen**、*パス*と*モード*引数 **_wfreopen**はワイド文字列です。 **_wfreopen**と **_freopen**動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen**|**freopen**|**freopen**|**_wfreopen**|

**freopen**は通常、既に開いているファイルのリダイレクトを使用**stdin**、 **stdout**、および**stderr**ユーザーによって指定されたファイルにします。 関連付けられている新しいファイル*ストリーム*を開くと*モード*、どのファイルは、次のように要求するアクセスの種類を指定する文字の文字列です。

|*モード*|アクセス|
|-|-|
| **"r"** | 読み取り用に開きます。 ファイルが存在しないか見つからない場合、 **freopen**呼び出しは失敗します。 |
| **"w"** | 書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。 |
| **"a"** | 末尾に書き込みができるようにファイルを開きます (追加モード)。EOF (end-of-file) マーカーを削除せずにファイルに新しいデータを書き込みます。 ファイルが存在しない場合は、作成します。 |
| **"r+"** | 読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。 |
| **"w+"** | 読み取りと書き込みの両方のモードで空のファイルを開きます。 そのファイルが既に存在すると、そのファイルの内容は破棄されます。 |
| **"a+"** | 読み取りと追加の両方のモードでファイルを開きます。 追加操作には、新しいデータをファイルに書き込む前に EOF マーカーを削除することが含まれます。 書き込みの完了後に、EOF マーカーは復元されません。 ファイルが存在しない場合は、作成します。 |

使用して、 **"w"** と **「w +」** 型は注意して既存のファイルを破棄するためです。

ファイルを開くと、 **"a"** または **「a +」** アクセスの種類、すべての書き込み、ファイルの最後に操作が行われます。 使用して、ファイル ポインターを移動できます[fseek](fseek-fseeki64.md)または[巻き戻し](rewind.md)、ファイル ポインターは常に戻す、ファイルの末尾には、書き込み操作の前にします。したがって、既存のデータは上書きされません。

**"A"** モードでは、ファイルを追加する前に EOF マーカーは削除されません。 追加が行われても、MS-DOS TYPE コマンドでは元の EOF マーカーまでのデータしか表示されず、ファイルに追加されたデータは表示されません。 **「A +」** モードでファイルに追加する前に EOF マーカーは削除します。 追加が終了すると、MS-DOS の TYPE コマンドでファイル内すべてのデータが表示されます。 **「A +」** モードが CTRL + Z EOF マーカーで終了するストリーム ファイルを追加するために必要です。

ときに、 **「r +」**、 **「w +」**、または **「a +」** アクセスの種類を指定すると、読み取りと書き込みの両方が許可されている (ファイルが開かれると言います"update")。 ただし、読み取りと書き込みを切り替える場合は、その前に [fsetpos](fsetpos.md)、[fseek](fseek-fseeki64.md)、または [rewind](rewind.md) のいずれかの関数を実行する必要があります。 現在の位置を指定することができます、 [fsetpos](fsetpos.md)または[fseek](fseek-fseeki64.md)必要な場合は、操作します。 上記の値だけでなく、次の文字の 1 つ含めることができます、*モード*改行の変換モードを指定する文字列。

|*モード*修飾子|変換モード|
|-|-|
| **t** | ファイルをテキスト (変換) モードで開きます。 |
| **b** | ファイルをバイナリ (無変換) モードで開きます。キャリッジ リターンとライン フィードの変換は行われません。 |

テキスト (変換) モードでは、キャリッジ リターンとラインフィード (CR-LF) の組み合わせが入力の 1 つのラインフィード (LF) 文字に変換されます。LF 文字は、出力時に CR-LF の組み合わせに変換されます。 また、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。 読み取りと書き込みの読み取り用または開かれたファイルで **「a +」**、ランタイム ライブラリは、ファイルの末尾に CTRL + Z をチェックし、可能であれば、それを削除します。 これを使用して、 [fseek](fseek-fseeki64.md)と[ftell](ftell-ftelli64.md)ファイル内で移動することがありますが[fseek](fseek-fseeki64.md)ファイルの末尾近くが正しく動作しません。 **T**オプションは、ANSI 互換が必要な場合は使用できません、Microsoft 拡張機能。

場合**t**または**b**には、指定しない*モード*、グローバル変数によって既定の変換モードが定義されている[_fmode](../../c-runtime-library/fmode.md)します。 場合**t**または**b**先頭に、引数、関数が失敗して返します**NULL**します。

テキスト モードと binary モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**freopen**|\<stdio.h>|
|**_wfreopen**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールがサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル**stdin**、 **stdout**、および**stderr**、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_freopen.c
// compile with: /W3
// This program reassigns stderr to the file
// named FREOPEN.OUT and writes a line to that file.
#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   // Reassign "stderr" to "freopen.out":
   stream = freopen( "freopen.out", "w", stderr ); // C4996
   // Note: freopen is deprecated; consider using freopen_s instead

   if( stream == NULL )
      fprintf( stdout, "error on freopen\n" );
   else
   {
      fprintf( stdout, "successfully reassigned\n" ); fflush( stdout );
      fprintf( stream, "This will go to the file 'freopen.out'\n" );
      fclose( stream );
   }
   system( "type freopen.out" );
}
```

```Output
successfully reassigned
This will go to the file 'freopen.out'
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[_fdopen、_wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
