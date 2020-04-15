---
title: _fsopen、_wfsopen
ms.date: 4/2/2020
api_name:
- _wfsopen
- _fsopen
- _o__fsopen
- _o__wfsopen
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
- wfsopen
- fsopen
- tfsopen
- _tfsopen
- _wfsopen
- _fsopen
helpviewer_keywords:
- opening files, streams
- fsopen function
- tfsopen function
- wfsopen function
- _fsopen function
- files [C++], opening
- _tfsopen function
- _wfsopen function
- file sharing [C++]
ms.assetid: 5e4502ab-48a9-4bee-a263-ebac8d638dec
ms.openlocfilehash: 49907808729375e3bea18a5f4bbf204852e0072a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345695"
---
# <a name="_fsopen-_wfsopen"></a>_fsopen、_wfsopen

ファイル共有付きでストリームを開きます。

## <a name="syntax"></a>構文

```C
FILE *_fsopen(
   const char *filename,
   const char *mode,
   int shflag
);
FILE *_wfsopen(
   const wchar_t *filename,
   const wchar_t *mode,
   int shflag
);
```

### <a name="parameters"></a>パラメーター

*Filename*<br/>
開くファイルの名前。

*モード*<br/>
アクセス許可の種類。

*シュフラッグ*<br/>
許可される共有の種類。

## <a name="return-value"></a>戻り値

これらの各関数は、ストリームへのポインターを返します。 エラーが発生すると、NULL のポインター値を返します。 *filename*または*mode*が**NULL**または空の文字列の場合、これらの関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、これらの関数は**NULL を**返し **、errno**を**EINVAL**に設定します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_fsopen**関数は *、filename*で指定されたファイルをストリームとして開き、mode 引数と*shflag*引数で定義された、後続の共有読み取りまたは書き込み用にファイルを準備します。 **_wfsopen**はワイド文字の **_fsopen**です。**_wfsopen**する*ファイル名*と*モード*の引数はワイド文字列です。 **_wfsopen**と **_fsopen**は、そうでなければ同じように動作します。

文字ストリング *・モード*は、次の表に示すように、ファイルに要求されるアクセスのタイプを指定します。

|期間|定義|
|----------|----------------|
|**"r"**|読み取り用に開きます。 ファイルが存在しないか、見つからない場合 **、_fsopen**呼び出しは失敗します。|
|**"w"**|書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。|
|**"a"**|ファイルの末尾への書き込み用にファイルを開きます (追加モード)。ファイルが存在しない場合は、まず、ファイルを作成します。|
|**"r+"**|読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。|
|**"w+"**|読み取りと書き込みの両方のモードで空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。|
|**"a+"**|読み取りおよび追加用にファイルを開きます。ファイルが存在しない場合は、まず、ファイルを作成します。|

**"w"** 型と **"w+" タイプ**は既存のファイルを破棄する可能性があるため、注意して使用してください。

**"a" または "a+"** **"a+"** アクセス タイプでファイルを開くと、すべての書き込み操作はファイルの最後に実行されます。 ファイル ポインタは[fseek](fseek-fseeki64.md)または[巻き戻し](rewind.md)を使用して再配置できますが、書き込み操作が実行される前に、常にファイルの末尾に戻されます。したがって、既存のデータを上書きすることはできません。 **"r+"** **、"w+"、** または **"a+"** アクセスタイプが指定されている場合、読み取りと書き込みの両方が許可されます (ファイルは更新用に開かれていると言われます)。 ただし、読み取りと書き込みを切り替える場合は、その前に [fsetpos](fsetpos.md)、[fseek](fseek-fseeki64.md)、または [rewind](rewind.md) のいずれかの操作を実行する必要があります。 必要に応じて[、fsetpos](fsetpos.md)または[fseek](fseek-fseeki64.md)操作に対して現在位置を指定できます。 上記の値に加えて、以下の文字のいずれかを*mode*に含めて、新しい行の変換モードを指定したり、ファイル管理に使用したりすることができます。

|期間|定義|
|----------|----------------|
|**T**|ファイルをテキスト (変換) モードで開きます。 このモードでは、復帰改行 (CR-LF) の組み合わせは入力時に単一ライン フィード (LF) に変換され、LF 文字は出力時に CR-LF の組み合わせに変換されます。 また、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。 読み取りまたは読み取り/書き込み用に開かれたファイルでは **、_fsopen**はファイルの末尾に Ctrl + Z をチェックし、可能であれば削除します。 これは[、fseek](fseek-fseeki64.md)と[ftell](ftell-ftelli64.md)を使用して、Ctrl + Z で終わるファイル内を移動すると[、fseek](fseek-fseeki64.md)がファイルの末尾付近で不適切に動作する可能性があるためです。|
|**B**|ファイルをバイナリ (無変換) モードで開き、前述の変換は行いません。|
|**S**|キャッシュがディスクからのシーケンシャル アクセスに最適化されるように指定します。ただし、シーケンシャル アクセスに限定されるわけではありません。|
|**R**|キャッシュがディスクからのランダム アクセスに最適化されるように指定します。ただし、ランダム アクセスに限定されるわけではありません。|
|**T**|ファイルを一時ファイルとして指定します。 可能な場合、ファイルはディスクにフラッシュされません。|
|**D**|ファイルを一時ファイルとして指定します。 最後のファイル ポインターが閉じられると、ファイルは削除されます。|

**t** または **b** を *mode* に指定しない場合、変換モードは既定のモード変数 **_fmode** によって定義されます。 **t**または**b**が引数の前に付く場合、関数は失敗し **、NULL**を返します。 テキスト モードとバイナリ モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。

引数*shflag*は、Share.h で定義されている次のマニフェスト定数の 1 つで構成される定数式です。

|期間|定義|
|----------|----------------|
|**_SH_COMPAT**|16 ビット アプリケーションの互換モードを設定します。|
|**_SH_DENYNO**|読み取りおよび書き込みアクセスを許可します。|
|**_SH_DENYRD**|ファイルへの読み取りアクセスを拒否します。|
|**_SH_DENYRW**|ファイルへの読み取りおよび書き込みアクセスを拒否します。|
|**_SH_DENYWR**|ファイルへの書き込みアクセスを拒否します。|

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfsopen**|**_fsopen**|**_fsopen**|**_wfsopen**|

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|省略可能なヘッダー|
|--------------|---------------------|----------------------|
|**_fsopen**|\<stdio.h>|\<share.h><br /><br /> *shflag*パラメータのマニフェスト定数の場合。|
|**_wfsopen**|\<stdio.h> または \<wchar.h>|\<share.h><br /><br /> *shflag*パラメータのマニフェスト定数の場合。|

## <a name="example"></a>例

```C
// crt_fsopen.c

#include <stdio.h>
#include <stdlib.h>
#include <share.h>

int main( void )
{
   FILE *stream;

   // Open output file for writing. Using _fsopen allows us to
   // ensure that no one else writes to the file while we are
   // writing to it.
    //
   if( (stream = _fsopen( "outfile", "wt", _SH_DENYWR )) != NULL )
   {
      fprintf( stream, "No one else in the network can write "
                       "to this file until we are done.\n" );
      fclose( stream );
   }
   // Now others can write to the file while we read it.
   system( "type outfile" );
}
```

```Output
No one else in the network can write to this file until we are done.
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[_fdopen、_wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[freopen、_wfreopen](freopen-wfreopen.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
[_sopen、_wsopen](sopen-wsopen.md)<br/>
