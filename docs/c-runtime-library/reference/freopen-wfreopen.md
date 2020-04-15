---
title: freopen、_wfreopen
ms.date: 4/2/2020
api_name:
- freopen
- _wfreopen
- _o__wfreopen
- _o_freopen
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
ms.openlocfilehash: 635775469ed6545abd6da43ba27d496d439f80ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345870"
---
# <a name="freopen-_wfreopen"></a>freopen、_wfreopen

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

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

これらの各関数は、新しく開かれたファイルへのポインターを返します。 エラーが発生した場合、元のファイルは閉じられ、関数は**NULL**ポインター値を返します。 *path*、 *mode*、または*stream*が null ポインターの場合、または*filename*が空の文字列の場合、これらの関数は無効なパラメーター ハンドラーを呼び[出します](../../c-runtime-library/parameter-validation.md)。 実行を続行できる場合、これらの関数は**errno**を**EINVAL**に設定し **、NULL**を返します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

これらの関数にはセキュリティが強化されたバージョンがあります。「[freopen_s、_wfreopen_s](freopen-s-wfreopen-s.md)」を参照してください。

**freopen**関数は、現在*stream*に関連付けられているファイルを閉じ *、path*で指定されたファイルに*ストリーム*を再割り当てします。 **_wfreopen**はワイド文字の **_freopen**です。**_wfreopen**する*パス*と*モード*の引数はワイド文字列です。 **_wfreopen**と **_freopen**は同じように動作します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen**|**freopen**|**freopen**|**_wfreopen**|

**freopen**は通常、事前に開かれているファイル**stdin**、 **stdout**、および**stderr**をユーザーが指定したファイルにリダイレクトするために使用されます。 *ストリーム**に関連*付けられた新しいファイルは、mode で開かれます。

|*モード*|アクセス|
|-|-|
| **"r"** | 読み取り用に開きます。 ファイルが存在しないか、見つからない場合、**フレオープン**呼び出しは失敗します。 |
| **"w"** | 書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。 |
| **"a"** | 末尾に書き込みができるようにファイルを開きます (追加モード)。EOF (end-of-file) マーカーを削除せずにファイルに新しいデータを書き込みます。 ファイルが存在しない場合は、作成します。 |
| **"r+"** | 読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。 |
| **"w+"** | 読み取りと書き込みの両方のモードで空のファイルを開きます。 そのファイルが既に存在すると、そのファイルの内容は破棄されます。 |
| **"a+"** | 読み取りと追加の両方のモードでファイルを開きます。 追加操作には、新しいデータをファイルに書き込む前に EOF マーカーを削除することが含まれます。 書き込みの完了後に、EOF マーカーは復元されません。 ファイルが存在しない場合は、作成します。 |

**"w"** 型と **"w+" タイプ**は既存のファイルを破棄する可能性があるため、注意して使用してください。

**"a" または "a+"** **"a+"** アクセス タイプでファイルを開くと、すべての書き込み操作はファイルの末尾で実行されます。 ファイル ポインタは[fseek](fseek-fseeki64.md)または[巻き戻し](rewind.md)を使用して再配置できますが、書き込み操作が実行される前に、ファイル ポインタは常にファイルの末尾に戻されます。したがって、既存のデータを上書きすることはできません。

**"a"** モードでは、ファイルに追加する前に EOF マーカーが削除されることはありません。 追加が行われても、MS-DOS TYPE コマンドでは元の EOF マーカーまでのデータしか表示されず、ファイルに追加されたデータは表示されません。 **"a+"** モードでは、ファイルに追加する前に EOF マーカーが削除されます。 追加が終了すると、MS-DOS の TYPE コマンドでファイル内すべてのデータが表示されます。 Ctrl + Z EOF マーカーで終了するストリーム ファイルに追加するには **、"a+"** モードが必要です。

**"r+"** **、"w+"、** または **"a+"** アクセスタイプが指定されている場合、読み取りと書き込みの両方が許可されます (ファイルは"更新"用に開かれていると言われます)。 ただし、読み取りと書き込みを切り替える場合は、その前に [fsetpos](fsetpos.md)、[fseek](fseek-fseeki64.md)、または [rewind](rewind.md) のいずれかの関数を実行する必要があります。 必要に応じて[、fsetpos](fsetpos.md)または[fseek](fseek-fseeki64.md)操作に対して現在位置を指定できます。 上記の値に加えて、次の文字のいずれかを*モード*文字列に含めて、新しい行の変換モードを指定できます。

|*モード*修飾子|翻訳モード|
|-|-|
| **T** | ファイルをテキスト (変換) モードで開きます。 |
| **B** | バイナリ (変換されていない) モードで開く。復帰文字と改行文字を含む変換は抑制されます。 |

テキスト (変換) モードでは、復帰改行 (CR-LF) の組み合わせは入力時に単一ライン フィード (LF) 文字に変換されます。LF 文字は出力時に CR-LF の組み合わせに変換されます。 また、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。 "a+" で読み取り用に開かれたファイル、または **"a+"** を使用して読み取るファイルでは、ランタイム ライブラリはファイルの末尾に Ctrl + Z が含まれるかどうかを確認し、可能であれば削除します。 これは[、fseek](fseek-fseeki64.md)と[ftell](ftell-ftelli64.md)を使用してファイル内を移動すると[、fseek](fseek-fseeki64.md)がファイルの末尾付近で不適切に動作する可能性があるためです。 **t**オプションは、ANSI の移植性が望ましい場合は使用しない Microsoft 拡張機能です。

**t**または**b**が*mode*で指定されていない場合、デフォルトの変換モードはグローバル変数[_fmode](../../c-runtime-library/fmode.md)によって定義されます。 **t**または**b**が引数の前に付く場合、関数は失敗し **、NULL**を返します。

テキスト モードとバイナリ モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**freopen**|\<stdio.h>|
|**_wfreopen**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールはサポートされていません。 コンソール **、stdin 、stdout**、および**stdout****stderr**に関連付けられている標準ストリーム ハンドルは、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
