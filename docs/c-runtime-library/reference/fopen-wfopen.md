---
title: fopen、_wfopen
ms.date: 4/2/2020
api_name:
- _wfopen
- fopen
- _o__wfopen
- _o_fopen
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
- fopen
- _wfopen
- _tfopen
- corecrt_wstdio/_wfopen
- stdio/fopen
helpviewer_keywords:
- opening files, for file I/O
- wfopen function
- tfopen function
- _tfopen function
- _wfopen function
- files [C++], opening
- fopen function
ms.assetid: e868993f-738c-4920-b5e4-d8f2f41f933d
ms.openlocfilehash: 4b9fa6542996b2c16128a841e2611b85e995be2a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346408"
---
# <a name="fopen-_wfopen"></a>fopen、_wfopen

ファイルを開きます。 追加のパラメーター検証を実行してエラー コードを返す、セキュリティが強化されたバージョンの機能が使用できます。「[fopen_s、_wfopen_s](fopen-s-wfopen-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
FILE *fopen(
   const char *filename,
   const char *mode
);
FILE *_wfopen(
   const wchar_t *filename,
   const wchar_t *mode
);
```

### <a name="parameters"></a>パラメーター

*Filename*<br/>
ファイル名。

*モード*<br/>
有効なアクセス種類。

## <a name="return-value"></a>戻り値

これらの各関数は、開いているファイルへのポインターを返します。 エラーが発生すると、NULL のポインター値を返します。 *filename*または*mode*が**NULL**または空の文字列の場合、これらの関数は無効なパラメータ ハンドラ[を](../../c-runtime-library/parameter-validation.md)トリガします。 実行を続行できる場合、これらの関数は**NULL を**返し **、errno**を**EINVAL**に設定します。

詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**fopen**関数は *、filename*で指定されたファイルを開きます。 既定では、狭い*ファイル名*文字列は ANSI コードページ (CP_ACP) を使用して解釈されます。 Windows デスクトップ アプリケーションでは、 [SetFileApisToOEM](/windows/win32/api/fileapi/nf-fileapi-setfileapistooem) 関数を使用して、これを OEM コード ページ (CP_OEMCP) に変更できます。 ファイル*名*が ANSI またはシステムの既定の OEM コードページを使用して解釈されるかどうかを判断するのには、[関数](/windows/win32/api/fileapi/nf-fileapi-arefileapisansi)を使用できます。 **_wfopen**は、ワイド文字バージョンの**fopen**です。**_wfopen**の引数はワイド文字列です。 それ以外の場合 **、_wfopen**と**開きは**同じように動作します。 **_wfopen**を使用するだけでは、ファイル ストリームで使用されるコード化文字セットには影響しません。

**fopen**は、実行時点でファイルシステム上で有効なパスを受け入れます。**fopen**は、コードを実行するシステムが実行時に共有またはマップされたドライブにアクセスできる限り、マップされたネットワークドライブに関連する UNC パスとパスを受け入れます。 **fopen**のパスを構築する場合は、実行環境でドライブ、パス、またはネットワーク共有が使用可能であることを確認します。 ディレクトリのパス区切り記号としてスラッシュ (/) または円記号 (\\) のどちらかを使用できます。

ファイルでその他の操作を実行する前には、必ず戻り値をチェックしてポインターが NULL かどうかを確認します。 エラーが発生した場合、グローバル変数**errno**が設定され、特定のエラー情報を取得するために使用される場合があります。 詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="unicode-support"></a>Unicode のサポート

**fopen は**ユニコードファイルストリームをサポートします。 Unicode ファイルを開くには、次のように **、fopen**に目的のエンコーディングを指定する**ccs**フラグを渡します。

> **ファイル\*fp = fopen("newfile.txt"、"rt+,ccs=**_エンコーディング_**");**

*エンコード*の値として **、UNICODE** **、UTF-8、****および UTF-16LE**が使用できます。

ファイルを Unicode モードで開くと、入力関数はファイルから読み込まれたデータを utf-16 データに変換**wchar_t。** Unicode モードで開かれたファイルに書き込む関数は、型として格納された UTF-16 データを含むバッファー **wchar_t**必要です。 ファイルが UTF-8 としてエンコードされている場合、UTF-16 データは書き込まれるときに UTF-8 に変換され、ファイルの UTF-8 でエンコードされた内容は読み取られるときに UTF-16 に変換されます。 Unicode モードで奇数バイトの読み取りまたは書き込みを試みると、 [パラメーター検証](../../c-runtime-library/parameter-validation.md) エラーが発生します。 UTF-8 としてプログラムに格納されたデータを読み取るか書き込む場合は、Unicode モードではなくテキストまたはバイナリ ファイル モードを使用します。 必要なエンコード変換は各自が行う必要があります。

既に存在するファイルを読み取り用または追加用に開く場合は、ファイル内にバイト順マーク (BOM: Byte Order Mark) があれば、それによってエンコーディングが決定されます。 BOM エンコードは **、ccs**フラグで指定されたエンコードよりも優先されます。 **CCS**エンコードは、BOM が存在しない場合、またはファイルが新しいファイルである場合にのみ使用されます。

> [!NOTE]
> BOM 検出は、Unicode モードで開かれたファイル (**つまり ccs**フラグを渡すことによって) にのみ適用されます。

次の表は、ファイル内の**fopen**およびバイト順序マークに指定されたさまざまな**ccs**フラグに使用されるモードをまとめたものです。

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>ccs フラグおよび BOM に基づいて使用されるエンコーディング

|ccs フラグ|BOM なし (または新しいファイル)|BOM: UTF-8|BOM: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**Unicode**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|

Unicode モードで書き込むように開かれたファイルには、自動的に BOM が書き込まれます。

*モード*が **"a, ccs=**_エンコーディング_**" の**場合 **、fopen**は読み取りアクセスと書き込みアクセスの両方を使用してファイルを開こうとします。 成功すると、この関数は BOM を読み取ってファイルのエンコーディングを決定します。失敗した場合は、ファイルに対して既定のエンコーディングを使用します。 いずれの場合も **、fopen**は書き込み専用アクセスを使用してファイルを再度開きます。 (これは **"a"** モードにのみ適用され **、"a+"** モードには適用されません)。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen**|**fopen**|**fopen**|**_wfopen**|

文字ストリング *・モード*は、ファイルに対して要求されるアクセスの種類を次のように指定します。

|*モード*|アクセス|
|-|-|
| **"r"** | 読み取り用に開きます。 ファイルが存在しないか、見つからない場合 **、fopen**呼び出しは失敗します。 |
| **"w"** | 書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。 |
| **"a"** | 末尾に書き込みができるようにファイルを開きます (追加モード)。EOF (end-of-file) マーカーを削除せずにファイルに新しいデータを書き込みます。 ファイルが存在しない場合は、作成します。 |
| **"r+"** | 読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。 |
| **"w+"** | 読み取りと書き込みの両方のモードで空のファイルを開きます。 そのファイルが既に存在すると、そのファイルの内容は破棄されます。 |
| **"a+"** | 読み取りと追加の両方のモードでファイルを開きます。 追加操作には、新しいデータをファイルに書き込む前に EOF マーカーを削除することが含まれます。 書き込みの完了後に、EOF マーカーは復元されません。 ファイルが存在しない場合は、作成します。 |

**"a"** アクセスタイプまたは **"a+"** アクセスタイプを使用してファイルを開くと、すべての書き込み操作はファイルの最後に行われます。 ファイル ポインタは[fseek](fseek-fseeki64.md)または[巻き戻し](rewind.md)を使用して再配置できますが、書き込み操作を実行する前に必ずファイルの末尾に戻されます。 したがって、既存のデータは上書きされません。

**"a"** モードでは、ファイルに追加される前に EOF マーカーが削除されることはありません。 追加が行われても、MS-DOS TYPE コマンドでは元の EOF マーカーまでのデータしか表示されず、ファイルに追加されたデータは表示されません。 ファイルに追加する前に **、"a+"** モードは EOF マーカーを削除します。 追加が終了すると、MS-DOS の TYPE コマンドでファイル内すべてのデータが表示されます。 Ctrl + Z EOF マーカーで終了するストリーム ファイルに追加するには **、"a+"** モードが必要です。

**"r+"** **、"w+"、** または **"a+"** アクセスタイプが指定されている場合、読み取りと書き込みの両方が有効になります (ファイルは"更新"用に開かれていると言われます)。 ただし、読み取りから書き込みに切り替えると、入力操作は EOF マーカーを検出する必要があります。 EOF がない場合、ファイル ポジショニング関数の中間の呼び出しを使用する必要があります。 ファイル位置決め関数は、 **fsetpos**、 [fseek](fseek-fseeki64.md)、および[巻き戻し です](rewind.md)。 書き込みから読み取りに切り替える場合は **、fflush**関数またはファイル位置決め関数の間に呼び出しを使用する必要があります。

前の値に加えて、次の文字を*mode*に追加して、改行文字の変換モードを指定できます。

|*モード*修飾子|翻訳モード|
|-|-|
| **T** | ファイルをテキスト (変換) モードで開きます。 |
| **B** | バイナリ (変換されていない) モードで開く。復帰文字と改行文字を含む変換は抑制されます。 |

テキスト モードでは、Ctrl キーを押しながら Z キーを押す文字は、入力時に EOF 文字として解釈されます。 **"a+" を**使用して読み取り/書き込み用に開かれているファイルでは **、fopen**はファイルの末尾にある Ctrl + Z をチェックし、可能であれば削除します。 これは[、fseek](fseek-fseeki64.md)と**ftell**を使用して Ctrl + Z で終わるファイル内を移動すると[、fseek](fseek-fseeki64.md)がファイルの末尾付近で正しく動作しなくなる可能性があるためです。

テキスト モードでは、復帰と改行の組み合わせは入力時に単一の改行に変換され、ライン フィード文字は出力時にキャリッジ リターンと改行の組み合わせに変換されます。 Unicode のストリーム入出力関数が既定のテキスト モードで動作すると、入力元または出力先のストリームはマルチバイト文字のシーケンスと仮定されます。 このため、Unicode ストリーム入力関数はマルチバイト文字をワイド文字に変換し、 **mbtowc** 関数を呼び出した場合と同様の効果を得ます。 同様の理由で、Unicode ストリーム出力関数は、 **wctomb** 関数が呼び出されたかのように、ワイド文字をマルチバイト文字に変換します。

**t**または**b**が*mode*で指定されていない場合、デフォルトの変換モードはグローバル変数[_fmode](../../c-runtime-library/fmode.md)によって定義されます。 **t**または**b**が引数の前に付く場合、関数は失敗し **、NULL**を返します。

Unicode およびマルチバイトのストリーム入出力でテキスト モードとバイナリ モードを使用する方法について詳しくは、「 [Text and Binary Mode File I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) 」および「 [Unicode Stream I/O in Text and Binary Modes](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)」をご覧ください。

次のオプションを*mode*に追加して、追加の動作を指定できます。

|*モード*修飾子|動作|
|-|-|
| **C** | **fflush**または **_flushall**が呼び出された場合にファイル・バッファーの内容がディスクに直接書き込まれるように、関連する*ファイル名*のコミット・フラグを使用可能にします。 |
| **n** | 関連付けられた*ファイル名*のコミット フラグを "no-commit" にリセットします。 これは既定値です。 プログラムを COMMODE.OBJ とリンクする場合は、グローバル コミット フラグもオーバーライドします。 プログラムを明示的に COMMODE.OBJ とリンクしない場合、グローバル コミット フラグの既定の設定は "コミットなし" です (「 [Link Options](../../c-runtime-library/link-options.md)」をご覧ください)。 |
| **N** | ファイルが子プロセスによって継承されないように指定します。 |
| **S** | キャッシュがディスクからのシーケンシャル アクセスに最適化されるように指定します。ただし、シーケンシャル アクセスに限定されるわけではありません。 |
| **R** | キャッシュがディスクからのランダム アクセスに最適化されるように指定します。ただし、ランダム アクセスに限定されるわけではありません。 |
| **T** | ファイルを一時ファイルとして指定します。 可能な場合、ファイルはディスクにフラッシュされません。 |
| **D** | ファイルを一時ファイルとして指定します。 最後のファイル ポインターが閉じられると、ファイルは削除されます。 |
| **ccs=**_エンコーディング_ | このファイルに使用するエンコード文字セット (UTF-8、UTF-16LE、または**UNICODE**のいずれか) を指定します。 **UTF-8** **UTF-16LE** 何も指定しない場合は、ANSI エンコーディングが使用されます。 |

**fopen**および **_fdopen**で使用される*モード*文字列の有効な文字は、[次のように_open](open-wopen.md)および[_sopen](sopen-wsopen.md)で使用される*oflag*引数に対応します。

|*モード*文字列の文字|オープン/\_オープンの場合\_の*ラグ*値に相当します|
|-------------------------------|----------------------------------------------------|
|**A**|**\_O\_WRONLY** &#124; ** \_O\_APPEND** (通常**\_は\_、O** ** \_CREAT\_** &#124; ** \_O\_APPEND**) &#124; WRONLY|
|**a+**|**\_O\_RDWR** &#124; ** \_O\_APPEND** (通常**\_は O\_RDWR** &#124; ** \_O\_APPEND** &#124; ** \_O\_CREAT** )|
|**R**|**\_O\_RDONLY**|
|**r+**|**\_O\_RDWR**|
|**W**|**\_O\_WRONLY** (通常**\_、O\_WRONLY** &#124; ** \_O\_CREAT** &#124; ** \_O\_TRUNC**)|
|**w+**|**\_O\_RDWR** (通常**\_は\_O RDWR** &#124; ** \_O\_CREAT** &#124; ** \_O\_TRUNC**)|
|**B**|**\_O\_バイナリー**|
|**T**|**\_O\_テキスト**|
|**C**|なし|
|**n**|なし|
|**S**|**\_O\_シーケンシャル**|
|**R**|**\_O\_ランダム**|
|**T**|**\_お\_お短命**|
|**D**|**\_O\_一時的な**|
|**ccs=ユニコード**|**\_O\_WTEXT**|
|**ccs=UTF-8**|**\_O\_UTF8**|
|**ccs=UTF-16LE**|**\_O\_UTF16**|

**rb**モードを使用している場合は、コードを移植する必要がなく、大きなファイルのほとんどを読み取る予定がある場合やネットワークのパフォーマンスを気にしていない場合は、オプションとしてメモリマップされた Win32 ファイルを使用するかどうかも検討してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**fopen**|\<stdio.h>|
|**_wfopen**|\<stdio.h> または \<wchar.h>|

**_wfopen**はマイクロソフトの拡張機能です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

**c**、 **n**、 **t**、 **S**、 **R**、 **T**、**および D**モードの各*オプション*は **、Fopen**および **_fdopen**用の Microsoft 拡張であり、ANSI 移植性が望ましい場合には使用しないでください。

## <a name="example-1"></a>例 1

次のプログラムは 2 ファイルを開きます。  **fclose**を使用して最初のファイルを閉じ、残りのファイルをすべて閉**じ_fcloseall。**

```C
// crt_fopen.c
// compile with: /W3
// This program opens two files. It uses
// fclose to close the first file and
// _fcloseall to close all remaining files.

#include <stdio.h>

FILE *stream, *stream2;

int main( void )
{
   int numclosed;

   // Open for read (will fail if file "crt_fopen.c" does not exist)
   if( (stream  = fopen( "crt_fopen.c", "r" )) == NULL ) // C4996
   // Note: fopen is deprecated; consider using fopen_s instead
      printf( "The file 'crt_fopen.c' was not opened\n" );
   else
      printf( "The file 'crt_fopen.c' was opened\n" );

   // Open for write
   if( (stream2 = fopen( "data2", "w+" )) == NULL ) // C4996
      printf( "The file 'data2' was not opened\n" );
   else
      printf( "The file 'data2' was opened\n" );

   // Close stream if it is not NULL
   if( stream)
   {
      if ( fclose( stream ) )
      {
         printf( "The file 'crt_fopen.c' was not closed\n" );
      }
   }

   // All other files are closed:
   numclosed = _fcloseall( );
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );
}
```

```Output
The file 'crt_fopen.c' was opened
The file 'data2' was opened
Number of files closed by _fcloseall: 1
```

## <a name="example-2"></a>例 2

次のプログラムでは、Unicode エンコーディングのテキスト モードで、ファイルを作成します (ファイルが存在する場合は上書きします)。  その後、2 つの文字列をファイルに書き込み、ファイルを閉じます。 _wfopen_test.xml というファイルが出力されます。このファイルには、出力セクションのデータが格納されます。

```C
// crt__wfopen.c
// compile with: /W3
// This program creates a file (or overwrites one if
// it exists), in text mode using Unicode encoding.
// It then writes two strings into the file
// and then closes the file.

#include <stdio.h>
#include <stddef.h>
#include <stdlib.h>
#include <wchar.h>

#define BUFFER_SIZE 50

int main(int argc, char** argv)
{
    wchar_t str[BUFFER_SIZE];
    size_t  strSize;
    FILE*   fileHandle;

    // Create an the xml file in text and Unicode encoding mode.
    if ((fileHandle = _wfopen( L"_wfopen_test.xml",L"wt+,ccs=UNICODE")) == NULL) // C4996
    // Note: _wfopen is deprecated; consider using _wfopen_s instead
    {
        wprintf(L"_wfopen failed!\n");
        return(0);
    }

    // Write a string into the file.
    wcscpy_s(str, sizeof(str)/sizeof(wchar_t), L"<xmlTag>\n");
    strSize = wcslen(str);
    if (fwrite(str, sizeof(wchar_t), strSize, fileHandle) != strSize)
    {
        wprintf(L"fwrite failed!\n");
    }

    // Write a string into the file.
    wcscpy_s(str, sizeof(str)/sizeof(wchar_t), L"</xmlTag>");
    strSize = wcslen(str);
    if (fwrite(str, sizeof(wchar_t), strSize, fileHandle) != strSize)
    {
        wprintf(L"fwrite failed!\n");
    }

    // Close the file.
    if (fclose(fileHandle))
    {
        wprintf(L"fclose failed!\n");
    }
    return 0;
}
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[_fdopen、_wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen、_wfreopen](freopen-wfreopen.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
[_sopen、_wsopen](sopen-wsopen.md)<br/>
