---
title: fopen_s、_wfopen_s
ms.date: 11/04/2016
apiname:
- _wfopen_s
- fopen_s
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
- fopen_s
- _tfopen_s
- _wfopen_s
helpviewer_keywords:
- _wfopen_s function
- opening files, for file I/O
- _tfopen_s function
- tfopen_s function
- wfopen_s function
- fopen_s function
- Unicode [C++], creating files
- Unicode [C++], writing files
- files [C++], opening
- Unicode [C++], files
ms.assetid: c534857e-39ee-4a3f-bd26-dfe551ac96c3
ms.openlocfilehash: 1309f991b8251bde7d614aa274d8d2e9da7a8ed3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333327"
---
# <a name="fopens-wfopens"></a>fopen_s、_wfopen_s

ファイルを開きます。 これらのバージョンの [fopen, _wfopen](fopen-wfopen.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンです。

## <a name="syntax"></a>構文

```C
errno_t fopen_s(
   FILE** pFile,
   const char *filename,
   const char *mode
);
errno_t _wfopen_s(
   FILE** pFile,
   const wchar_t *filename,
   const wchar_t *mode
);
```

### <a name="parameters"></a>パラメーター

*pFile*<br/>
開かれたファイルへのポインターを受け取るファイル ポインターへのポインター。

*ファイル名*<br/>
ファイル名。

*モード*<br/>
アクセス許可の種類。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。 これらのエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

### <a name="error-conditions"></a>エラー条件

|*pFile*|*ファイル名*|*モード*|戻り値|内容*pFile*|
|-------------|----------------|------------|------------------|------------------------|
|**NULL**|任意|任意|**EINVAL**|変更なし|
|任意|**NULL**|任意|**EINVAL**|変更なし|
|任意|任意|**NULL**|**EINVAL**|変更なし|

## <a name="remarks"></a>Remarks

によって開かれたファイル**fopen_s**と **_wfopen_s**は共有できません。 ファイルが共有されることを必要とする場合[_fsopen、_wfsopen](fsopen-wfsopen.md)な適切な共有モード定数 — たとえば、 **_SH_DENYNO**読み取り/書き込み共有の。

**Fopen_s**関数で指定されているファイルが開きます*filename*します。 **_wfopen_s**のワイド文字バージョンは、 **fopen_s**; 引数 **_wfopen_s**はワイド文字列です。 **_wfopen_s**と**fopen_s**動作は同じです。

**fopen_s**の実行時にファイル システムでは有効なパスを受け取りますUNC パスとをマップ済みネットワーク ドライブを含むパスでは受け入れ**fopen_s**限り、コードを実行して、システムは、共有へのアクセスを持っているか、実行時にマップ済みネットワーク ドライブ。 パスを構築する際に**fopen_s**、ドライブ、パス、可用性に関する前提条件を作成しない、または実行時環境のネットワークと共有します。 ディレクトリのパス区切り記号としてスラッシュ (/) または円記号 (\\) のどちらかを使用できます。

これらの関数では、パラメーターの検証が行われます。 場合*pFile*、 *filename*、または*モード*null ポインターの場合は、」の説明に従って、これらの関数は、無効なパラメーター例外を生成[パラメーターの検証](../../c-runtime-library/parameter-validation.md).

ファイルでその他の操作を実行する前には、必ず戻り値をチェックして関数が成功したかどうかを確認します。 エラー コードが返されるエラーが発生する場合とグローバル変数**errno**設定されます。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="unicode-support"></a>Unicode のサポート

**fopen_s** Unicode のファイル ストリームをサポートしています。 新規または既存の Unicode ファイルを開くには、渡す、 *ccs*に目的のエンコーディングを指定するフラグ**fopen_s**:

**fopen_s(&fp, "newfile.txt", "rw, ccs=**_encoding_**");**

値を許可*エンコード*は**UNICODE**、 **utf-8**、および**UTF 16LE**します。 ある値を指定しない場合の*エンコード*、 **fopen_s**は ANSI エンコーディングを使用します。

既に存在するファイルを読み取り用または追加用に開く場合は、ファイル内にバイト順マーク (BOM: Byte Order Mark) があれば、それによってエンコーディングが決定されます。 BOM エンコーディングよりも優先されるエンコードによって指定されるは、 *ccs*フラグ。 *Ccs*存在またはファイルが新しいファイルに BOM がない場合にのみ使用がエンコードされます。

> [!NOTE]
> BOM 検出は、Unicode モードで開かれたファイルにのみ適用されます。つまりを渡して、 *ccs*フラグ。

次の表は、さまざまなモードを示します*ccs*フラグに指定されている**fopen_s**とファイルのバイト順序マークします。

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>ccs フラグおよび BOM に基づいて使用されるエンコーディング

|ccs フラグ|BOM なし (または新しいファイル)|BOM:UTF-8|BOM:UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**UNICODE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|

Unicode モードで書き込むように開かれたファイルには、自動的に BOM が書き込まれます。

場合*モード*は **"、ccs =**_エンコード_**"**、 **fopen_s**読み書きの両方で、ファイルを開くには、まずアクセスおよび書き込みアクセス。 成功すると、この関数は BOM を読み取ってファイルのエンコーディングを決定します。失敗した場合は、ファイルに対して既定のエンコーディングを使用します。 いずれの場合も、 **fopen_s**再書き込み専用アクセス権を持つファイルを開きます。 (これに適用されます **、** モードのみ、not **+**)。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen_s**|**fopen_s**|**fopen_s**|**_wfopen_s**|

文字の文字列*モード*ファイルは、次のように要求するアクセスの種類を指定します。

|*モード*|アクセス|
|-|-|
| **"r"** | 読み取り用に開きます。 ファイルが存在しないか見つからない場合、 **fopen_s**呼び出しは失敗します。 |
| **"w"** | 書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。 |
| **"a"** | 末尾に書き込みができるようにファイルを開きます (追加モード)。EOF (end-of-file) マーカーを削除せずにファイルに新しいデータを書き込みます。 ファイルが存在しない場合は、作成します。 |
| **"r+"** | 読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。 |
| **"w+"** | 読み取りと書き込みの両方のモードで空のファイルを開きます。 そのファイルが既に存在すると、そのファイルの内容は破棄されます。 |
| **"a+"** | 読み取りと追加の両方のモードでファイルを開きます。 追加操作には、新しいデータをファイルに書き込む前に EOF マーカーを削除することが含まれます。 書き込みの完了後に、EOF マーカーは復元されません。 ファイルが存在しない場合は、作成します。 |

使用してファイルを開くと、 **"a"** または **「a +」** アクセスの種類、すべての書き込み操作、ファイルの末尾から行われます。 使用して、ファイル ポインターの位置を変更できる[fseek](fseek-fseeki64.md)または[巻き戻し](rewind.md)、これは常に、ファイルの末尾に前に戻さ、書き込み操作が既存のデータを上書きすることはできません。

**"A"** モードでは、ファイルを追加する前に EOF マーカーは削除されません。 追加が行われても、MS-DOS TYPE コマンドでは元の EOF マーカーまでのデータしか表示されず、ファイルに追加されたデータは表示されません。 **「A +」** モードでファイルに追加する前に EOF マーカーは削除します。 追加が終了すると、MS-DOS の TYPE コマンドでファイル内すべてのデータが表示されます。 **「A +」** モードが CTRL + Z EOF マーカーを使用して終了するストリーム ファイルを追加するために必要です。

ときに、 **「r +」**、 **「w +」**、または **「a +」** アクセスの種類を指定すると、読み取りと書き込みの両方を許可します。 (ファイルは "更新" モードで開きます)。ただし、読み取りから書き込みに切り替えると、入力操作は EOF マーカーを検出する必要があります。 EOF がない場合、ファイル ポジショニング関数の中間の呼び出しを使用する必要があります。 ファイル ポジショニング関数は**fsetpos**、 [fseek](fseek-fseeki64.md)、および[巻き戻し](rewind.md)します。 書き込みから読み取りに切り替えたときに中間の呼び出しを使用する必要があります**fflush**またはファイル ポジショニング関数。

上記の値のほかに、次の文字を含めることが*モード*改行文字の変換モードを指定します。

|*モード*修飾子|変換モード|
|-|-|
| **t** | ファイルをテキスト (変換) モードで開きます。 |
| **b** | ファイルをバイナリ (無変換) モードで開きます。キャリッジ リターンとライン フィードの変換は行われません。 |

テキスト (変換) モードでは、CTRL + Z は入力ファイルの終端文字として解釈されます。 ファイルを読み取り/書き込みで開いた **「a +」**、 **fopen_s**ファイルの末尾に CTRL + Z をチェックし、可能であれば削除します。 これを使用して、 [fseek](fseek-fseeki64.md)と**ftell** CTRL + Z で終わるを引き起こす可能性のあるファイル内で移動する[fseek](fseek-fseeki64.md)ファイルの末尾近くが正しく動作しません。

また、テキスト モードで復帰と改行の組み合わせは、入力、1 つの改行に変換し、改行文字は出力に復帰と改行の組み合わせに変換します。 Unicode のストリーム入出力関数が既定のテキスト モードで動作すると、入力元または出力先のストリームはマルチバイト文字のシーケンスと仮定されます。 このため、Unicode ストリーム入力関数はマルチバイト文字をワイド文字に変換し、 **mbtowc** 関数を呼び出した場合と同様の効果を得ます。 同様の理由で、Unicode ストリーム出力関数は、 **wctomb** 関数が呼び出されたかのように、ワイド文字をマルチバイト文字に変換します。

場合**t**または**b**には、指定しない*モード*、グローバル変数によって既定の変換モードが定義されている[_fmode](../../c-runtime-library/fmode.md)します。 場合**t**または**b**先頭に、引数、関数が失敗して返します**NULL**します。

Unicode およびマルチバイトのストリーム入出力におけるテキスト モードおよびバイナリ モードの使い方の詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」および「[テキスト モードとバイナリ モードの Unicode ストリーム入出力](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)」を参照してください。

|*モード*修飾子|動作|
|-|-|
| **c** | 関連付けられているコミット フラグを有効にする*filename*ファイル バッファーの内容がいずれかのディスクに直接書き込まれるように**fflush**または **_flushall**が呼び出されます。 |
| **n** | 関連付けられているコミット フラグをリセット*filename* 「コミットなし」。 既定値です。 プログラムを COMMODE.OBJ とリンクする場合は、グローバル コミット フラグもオーバーライドします。 プログラムを明示的に COMMODE.OBJ とリンクしない場合、グローバル コミット フラグの既定の設定は "コミットなし" です (「 [Link Options](../../c-runtime-library/link-options.md)」をご覧ください)。 |
| **N** | ファイルが子プロセスによって継承されないように指定します。 |
| **S** | キャッシュがディスクからのシーケンシャル アクセスに最適化されるように指定します。ただし、シーケンシャル アクセスに限定されるわけではありません。 |
| **R** | キャッシュがディスクからのランダム アクセスに最適化されるように指定します。ただし、ランダム アクセスに限定されるわけではありません。 |
| **T** | ファイルを一時ファイルとして指定します。 可能な場合、ファイルはディスクにフラッシュされません。 |
| **D** | ファイルを一時ファイルとして指定します。 最後のファイル ポインターが閉じられると、ファイルは削除されます。 |
| **ccs=**_encoding_ | 使用する設定でエンコードされた文字を指定します (いずれかの**utf-8**、 **UTF 16LE**、または**UNICODE**) このファイル。 何も指定しない場合は、ANSI エンコーディングが使用されます。 |

有効な文字は、*モード*で使用される文字列**fopen_s**と[_fdopen](fdopen-wfdopen.md)に対応して*oflag*で使用される引数[_開く](open-wopen.md)と[_sopen](sopen-wsopen.md)、次のようにします。

|文字*モード*文字列|等価*oflag*開く (_o)/_sopen の値|
|-------------------------------|----------------------------------------------------|
|**a**|**_O_WRONLY** &#124; **_O_APPEND** (usually **_O_WRONLY** &#124; **_O_CREAT** &#124;** _O_APPEND**)|
|**+**|**_O_RDWR** &#124; **_O_APPEND** (usually **_O_RDWR** &#124; **_O_APPEND** &#124; **_O_CREAT** )|
|**r**|**_O_RDONLY**|
|**r+**|**_O_RDWR**|
|**w**|**_O_WRONLY** (usually **_O_WRONLY** &#124; **_O_CREAT** &#124;** _O_TRUNC**)|
|**w +**|**_O_RDWR** (usually **_O_RDWR** &#124; **_O_CREAT** &#124; **_O_TRUNC**)|
|**b**|**_O_BINARY**|
|**t**|**_O_TEXT**|
|**c**|なし|
|**n**|なし|
|**S**|**_O_SEQUENTIAL**|
|**R**|**_O_RANDOM**|
|**T**|**_O_SHORTLIVED**|
|**D**|**_O_TEMPORARY**|
|**ccs=UNICODE**|**_O_WTEXT**|
|**ccs=UTF-8**|**_O_UTF8**|
|**ccs=UTF-16LE**|**_O_UTF16**|

使用する場合**rb**モードは、コードを移植して、大量のファイルを読み取る必要はありませんやネットワークのパフォーマンスは気にしない、Win32 メモリ マップト ファイルはオプションにもあります。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**fopen_s**|\<stdio.h>|
|**_wfopen_s**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

**C**、 **n**、および**t** *モード*オプション用の Microsoft 拡張機能は、 **fopen_s**と[_fdopen](fdopen-wfdopen.md) ANSI 互換が必要な場合は使用する必要があります。

## <a name="example"></a>例

```C
// crt_fopen_s.c
// This program opens two files. It uses
// fclose to close the first file and
// _fcloseall to close all remaining files.

#include <stdio.h>

FILE *stream, *stream2;

int main( void )
{
   errno_t err;

   // Open for read (will fail if file "crt_fopen_s.c" does not exist)
   err  = fopen_s( &stream, "crt_fopen_s.c", "r" );
   if( err == 0 )
   {
      printf( "The file 'crt_fopen_s.c' was opened\n" );
   }
   else
   {
      printf( "The file 'crt_fopen_s.c' was not opened\n" );
   }

   // Open for write
   err = fopen_s( &stream2, "data2", "w+" );
   if( err == 0 )
   {
      printf( "The file 'data2' was opened\n" );
   }
   else
   {
      printf( "The file 'data2' was not opened\n" );
   }

   // Close stream if it is not NULL
   if( stream )
   {
      err = fclose( stream );
      if ( err == 0 )
      {
         printf( "The file 'crt_fopen_s.c' was closed\n" );
      }
      else
      {
         printf( "The file 'crt_fopen_s.c' was not closed\n" );
      }
   }

   // All other files are closed:
   int numclosed = _fcloseall( );
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );
}
```

```Output
The file 'crt_fopen_s.c' was opened
The file 'data2' was opened
Number of files closed by _fcloseall: 1
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[_fdopen、_wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen、_wfreopen](freopen-wfreopen.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
