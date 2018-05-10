---
title: _fsopen、_wfsopen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wfsopen
- _fsopen
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
- wfsopen
- fsopen
- tfsopen
- _tfsopen
- _wfsopen
- _fsopen
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ce69c6789ba65f61c54957dde3dfa6965bc32e2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="fsopen-wfsopen"></a>_fsopen、_wfsopen

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

*ファイル名*<br/>
開くファイルの名前。

*モード*<br/>
アクセス許可の種類。

*shflag*<br/>
許可される共有の種類。

## <a name="return-value"></a>戻り値

これらの各関数は、ストリームへのポインターを返します。 エラーが発生すると、NULL のポインター値を返します。 場合*filename*または*モード*は**NULL**または空の文字列、これらの関数の呼び出しに無効なパラメーター ハンドラー」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md). これらの関数を返すかどうかは、引き続き実行が許可された、 **NULL**設定と**errno**に**EINVAL**です。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

**_Fsopen**関数は指定されたファイルを開きます*filename*をストリームとしてモードの定義に従って、後続の共有読み取りまたは書き込みのファイルを準備および*shflag*引数。 **_wfsopen**のワイド文字バージョンは、 **_fsopen**以外の場合は、 *filename*と*モード*引数 **_wfsopen**はワイド文字列です。 **_wfsopen**と **_fsopen**それ以外の場合の動作は同じです。

文字の文字列*モード*次の表に示すように、ファイルは、要求されたアクセスの種類を指定します。

|用語|定義|
|----------|----------------|
|**"r"**|読み取り用に開きます。 ファイルが存在しないかを検出できない場合、 **_fsopen**呼び出しは失敗します。|
|**"w"**|書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。|
|**"a"**|ファイルの末尾への書き込み用にファイルを開きます (追加モード)。ファイルが存在しない場合は、まず、ファイルを作成します。|
|**"r+"**|読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。|
|**"w+"**|読み取りと書き込みの両方のモードで空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。|
|**"a+"**|読み取りおよび追加用にファイルを開きます。ファイルが存在しない場合は、まず、ファイルを作成します。|

使用して、 **"w"** と**「w +」**既存のファイルを破棄するための型は注意します。

使用するファイルを開くと、 **"a"** または**「a +」**アクセスの種類、すべての書き込み操作、ファイルの末尾から行われます。 使用して、ファイル ポインターを移動できる[fseek](fseek-fseeki64.md)または[巻き戻し](rewind.md)が、常に戻さファイルの末尾には、書き込み操作の前にします。したがって、既存のデータは上書きされません。 ときに、 **「r +」**、 **「w +」**、または**「a +」**アクセスの種類を指定すると、読み取りと書き込みの両方が許可されている (ファイルは更新プログラムの開いていると考えられます)。 ただし、読み取りと書き込みを切り替える場合は、その前に [fsetpos](fsetpos.md)、[fseek](fseek-fseeki64.md)、または [rewind](rewind.md) のいずれかの操作を実行する必要があります。 現在の位置を指定することができます、 [fsetpos](fsetpos.md)または[fseek](fseek-fseeki64.md)必要な場合は、操作します。 上記の値に加え、次の文字のいずれかに記述できます*モード*新しい線、およびファイルの管理の変換モードを指定します。

|用語|定義|
|----------|----------------|
|**t**|ファイルをテキスト (変換) モードで開きます。 このモードでは、キャリッジ リターンとライン フィード (CR-LF) の組み合わせは入力時に 1 つの改行 (LF) に変換し、LF 文字は出力時に CR-LF の組み合わせに変換します。 また、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。 読み取りまたは読み取り/書き込み用に開かれたファイルで **_fsopen**ファイルの末尾に CTRL + Z が確認され、削除可能な場合は削除します。 これは、使用するため[fseek](fseek-fseeki64.md)と[ftell](ftell-ftelli64.md) CTRL + Z で終わる可能性があるファイル内で移動する[fseek](fseek-fseeki64.md)が、ファイルの末尾付近に正しく動作します。|
|**b**|ファイルをバイナリ (無変換) モードで開き、前述の変換は行いません。|
|**S**|キャッシュがディスクからのシーケンシャル アクセスに最適化されるように指定します。ただし、シーケンシャル アクセスに限定されるわけではありません。|
|**R**|キャッシュがディスクからのランダム アクセスに最適化されるように指定します。ただし、ランダム アクセスに限定されるわけではありません。|
|**T**|ファイルを一時ファイルとして指定します。 可能な場合、ファイルはディスクにフラッシュされません。|
|**D**|ファイルを一時ファイルとして指定します。 最後のファイル ポインターが閉じられると、ファイルは削除されます。|

**t** または **b** を *mode* に指定しない場合、変換モードは既定のモード変数 **_fmode** によって定義されます。 場合**t**または**b**は先頭に、引数、関数が失敗して返します**NULL**です。 テキスト モードと binary モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。

引数*shflag* Share.h で定義されている、次のマニフェスト定数のいずれかで構成される定数式です。

|用語|定義|
|----------|----------------|
|**_SH_COMPAT**|16 ビット アプリケーションの互換モードを設定します。|
|**_SH_DENYNO**|読み取りおよび書き込みアクセスを許可します。|
|**_SH_DENYRD**|ファイルへの読み取りアクセスを拒否します。|
|**_SH_DENYRW**|ファイルへの読み取りおよび書き込みアクセスを拒否します。|
|**_SH_DENYWR**|ファイルへの書き込みアクセスを拒否します。|

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfsopen**|**_fsopen**|**_fsopen**|**_wfsopen**|

## <a name="requirements"></a>要件

|関数|必須ヘッダー|省略可能なヘッダー|
|--------------|---------------------|----------------------|
|**_fsopen**|\<stdio.h>|\<share.h><br /><br /> 用のマニフェスト定数の*shflag*パラメーター。|
|**_wfsopen**|\<stdio.h> または \<wchar.h>|\<share.h><br /><br /> 用のマニフェスト定数の*shflag*パラメーター。|

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
