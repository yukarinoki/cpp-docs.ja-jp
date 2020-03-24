---
title: _open、_wopen
ms.date: 11/04/2016
api_name:
- _open
- _wopen
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wopen
- _topen
- _open
helpviewer_keywords:
- opening files, for file I/O
- topen function
- _open function
- _topen function
- _wopen function
- files [C++], opening
- wopen function
- open function
ms.assetid: 13f6a0c3-d1aa-450d-a7aa-74abc91b163e
ms.openlocfilehash: 4ce6e9aebe5d058143ad737f9c9db5bb68b30b1f
ms.sourcegitcommit: eff68e4e82be292a5664616b16a526df3e9d1cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80150728"
---
# <a name="_open-_wopen"></a>_open、_wopen

ファイルを開きます。 セキュリティが強化されたバージョンを使用できるようになったため、これらの関数は非推奨とされています。「[_sopen_s、_wsopen_s](sopen-s-wsopen-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _open(
   const char *filename,
   int oflag [,
   int pmode]
);
int _wopen(
   const wchar_t *filename,
   int oflag [,
   int pmode]
);
```

### <a name="parameters"></a>パラメーター

*filename*<br/>
ファイル名。

*oflag*<br/>
許可される操作の種類。

*pmode*<br/>
アクセス許可モード。

## <a name="return-value"></a>戻り値

これらの各関数は、開かれたファイルのファイル記述子を返します。 戻り値-1 はエラーを示します。その場合、 **errno**は次のいずれかの値に設定されます。

|errno の値|条件|
|-|-|
| **EACCES** | 読み取り専用ファイルを書き込み用に開こうとしたか、指定された操作がファイルの共有モードで許可されていないか、指定されたパスがディレクトリです。 |
| **EEXIST** | **_O_CREAT**と **_O_EXCL**フラグが指定されていますが、 *filename*は既に存在します。 |
| **EINVAL** | *Oflag*または*pmode*引数が無効です。 |
| **EMFILE** | ファイル記述子をこれ以上使用できません (開かれているファイルが多すぎます)。 |
| **ENOENT** | ファイルまたはパスが見つかりません。 |

これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

**_Open**関数は、 *filename*で指定されたファイルを開き、 *oflag*で指定されているように読み取りまたは書き込み用に準備します。 **_wopen**は **_open**のワイド文字バージョンです。 **_wopen**する*filename*引数は、ワイド文字列です。 **_wopen**と **_open**は同じように動作します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_topen**|**_open**|**_open**|**_wopen**|

*oflag*は、> \<で定義されている次のマニフェスト定数または定数の組み合わせの1つ以上から形成される整数式です。

|*oflag*定数|動作|
|-|-|
| **_O_APPEND** | 書き込み操作の前に、毎回、ファイル ポインターをファイルの末尾に移動します。 |
| **_O_BINARY** | ファイルをバイナリ (無変換) モードで開きます。 (バイナリ モードの詳細については、「[fopen](fopen-wfopen.md)」を参照してください)。 |
| **_O_CREAT** | ファイルを作成し、書き込み用に開きます。 *Filename*によって指定されたファイルが存在する場合は効果がありません。 **_O_CREAT**が指定されている場合は、 *pmode*引数が必要です。 |
| **_O_CREAT** &#124; **_O_SHORT_LIVED** | ファイルを一時ファイルとして作成し、可能な場合は、ディスクにフラッシュしません。 **_O_CREAT**が指定されている場合は、 *pmode*引数が必要です。 |
| **_O_CREAT** &#124; **_O_TEMPORARY** | ファイルを一時ファイルとして作成します。最後のファイル記述子が閉じられると、ファイルは削除されます。 **_O_CREAT**が指定されている場合は、 *pmode*引数が必要です。 |
| **_O_CREAT** &#124; `_O_EXCL` | *Filename*によって指定されたファイルが存在する場合、エラー値を返します。 **_O_CREAT**と共に使用する場合にのみ適用されます。 |
| **_O_NOINHERIT** | 共有ファイル記述子の作成を禁止します。 |
| **_O_RANDOM** | キャッシュがディスクからのランダム アクセスに最適化されるように指定します。ただし、ランダム アクセスに限定されるわけではありません。 |
| **_O_RDONLY** | 読み取り専用でファイルを開きます。 **_O_RDWR**または **_O_WRONLY**と共に指定することはできません。 |
| **_O_RDWR** | 読み取りと書き込みの両方用にファイルを開きます。 **_O_RDONLY**または **_O_WRONLY**と共に指定することはできません。 |
| **_O_SEQUENTIAL** | キャッシュがディスクからのシーケンシャル アクセスに最適化されるように指定します。ただし、シーケンシャル アクセスに限定されるわけではありません。 |
| **_O_TEXT** | ファイルをテキスト (変換) モードで開きます。 (詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」および「[fopen](fopen-wfopen.md)」を参照してください。) |
| **_O_TRUNC** | ファイルを開き、長さゼロに切り詰めます。ファイルに書き込みアクセス許可が必要です。 **_O_RDONLY**と共に指定することはできません。 **_O_CREAT**と共に使用 **_O_TRUNC** 、既存のファイルを開くか、ファイルを作成します。 **注:** **_O_TRUNC**フラグは、指定されたファイルの内容を破棄します。 |
| **_O_WRONLY** | 書き込み専用でファイルを開きます。 **_O_RDONLY**または **_O_RDWR**と共に指定することはできません。 |
| **_O_U16TEXT** | Unicode UTF-16 モードでファイルを開きます。 |
| **_O_U8TEXT** | Unicode UTF-8 モードでファイルを開きます。 |
| **_O_WTEXT** | Unicode モードでファイルを開きます。 |

ファイルアクセスモードを指定するには、 **_O_RDONLY**、 **_O_RDWR**、 **_O_WRONLY**のいずれかを指定する必要があります。 アクセス モードに既定値はありません。

読み取り用にファイルを開くために **_O_WTEXT**を使用する場合、 **_open**はファイルの先頭を読み取り、バイトオーダーマーク (BOM) を確認します。 BOM がある場合、ファイルは BOM に応じて UTF-8 または UTF-16LE として扱われます。 BOM がない場合、ファイルは ANSI として扱われます。 **_O_WTEXT**を使用してファイルを書き込み用に開くと、utf-16 が使用されます。 以前の設定またはバイトオーダーマークに関係なく、 **_O_U8TEXT**を使用すると、ファイルは常に utf-8 として開かれます。 **_O_U16TEXT**を使用する場合、ファイルは常に utf-16 として開かれます。

**_O_WTEXT**、 **_O_U8TEXT**、または **_O_U16TEXT**を使用してファイルが Unicode モードで開かれると、入力関数は、ファイルから読み取られたデータを、型**wchar_t**として格納された utf-16 データに変換します。 Unicode モードで開かれたファイルに書き込む関数は、型**wchar_t**として格納された utf-16 データを含むバッファーを想定します。 ファイルが UTF-8 としてエンコードされている場合、UTF-16 データは書き込まれるときに UTF-8 に変換され、ファイルの UTF-8 でエンコードされた内容は読み取られるときに UTF-16 に変換されます。 Unicode モードで奇数バイトの読み取りまたは書き込みを試みると、パラメーター検証エラーが発生します。 UTF-8 としてプログラムに格納されたデータを読み取るか書き込む場合は、Unicode モードではなくテキストまたはバイナリ ファイル モードを使用します。 必要なエンコード変換は各自が行う必要があります。

**_Open**が **_O_WRONLY** |  **_O_APPEND** (追加モード) と **_O_WTEXT**、 **_O_U16TEXT**、または **_O_U8TEXT**で呼び出された場合、まず読み取りと書き込みのためにファイルを開こうとし、BOM を読み取り、書き込み専用でもう一度開きます。 読み取りおよび書き込み用にファイルを開くのに失敗した場合、書き込み専用でファイルを開き、Unicode モード設定の既定値を使用します。

2つ以上のマニフェスト定数を使用して*oflag*引数を指定すると、定数はビットごとの or 演算子 ( **&#124;** ) と組み合わされます。 バイナリ モードとテキスト モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。

*Pmode*引数は **_O_CREAT**が指定されている場合にのみ必要です。 ファイルが既に存在する場合、 *pmode*は無視されます。 それ以外の場合、 *pmode*では、ファイルのアクセス許可の設定を指定します。この設定は、新しいファイルが最初に閉じられたときに設定されます。 **_open**は、アクセス許可が設定される前に、現在のファイルアクセス許可マスクを*pmode*に適用します。 (詳細については、「 [_umask](umask.md)」を参照してください)。*pmode*は、\<sys> で定義されている次のマニフェスト定数のいずれかまたは両方を含む整数式です。

|*pmode*|意味|
|-|-|
| **_S_IREAD** | 読み取りのみが許可されます。 |
| **_S_IWRITE** | 書き込みが許可されます。 (実際には、読み取りと書き込みが許可されます)。 |
| **_S_IREAD** &#124; **_S_IWRITE** | 読み取りと書き込みが許可されます。 |

両方の定数が指定されている場合は、ビットごとの OR **&#124;** 演算子 () と結合されます。 Windows では、すべてのファイルは読み取り可能です。書き込み専用のアクセス許可は使用できません。 したがって、 **_S_IWRITE**と **_S_IREAD** |  **_S_IWRITE**のモードは同等です。

**_S_IREAD**と **_S_IWRITE**の一部の組み合わせ以外の値が、*別のオペレーティング*システムで有効な*pmode*を指定する場合でも、または、allowed *oflag* values 以外の値を指定した場合、関数はデバッグモードでアサーションを生成し、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、この関数は-1 を返し、 **errno**を**EINVAL**に設定します。

## <a name="requirements"></a>要件

|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|---------------------|
|**_open**|\<io.h>|\<fcntl.h>、\<sys\types.h>、\<sys\stat.h>|
|**_wopen**|\<io.h> または \<wchar.h>|\<fcntl.h>、\<sys\types.h>、\<sys\stat.h>|

**_open**と **_wopen**は Microsoft の拡張機能です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_open.c
// compile with: /W3
/* This program uses _open to open a file
* named CRT_OPEN.C for input and a file named CRT_OPEN.OUT
* for output. The files are then closed.
*/
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>

int main( void )
{
   int fh1, fh2;

   fh1 = _open( "CRT_OPEN.C", _O_RDONLY ); // C4996
   // Note: _open is deprecated; consider using _sopen_s instead
   if( fh1 == -1 )
      perror( "Open failed on input file" );
   else
   {
      printf( "Open succeeded on input file\n" );
      _close( fh1 );
   }

   fh2 = _open( "CRT_OPEN.OUT", _O_WRONLY | _O_CREAT, _S_IREAD |
                            _S_IWRITE ); // C4996
   if( fh2 == -1 )
      perror( "Open failed on output file" );
   else
   {
      printf( "Open succeeded on output file\n" );
      _close( fh2 );
   }
}
```

### <a name="output"></a>出力

```Output
Open succeeded on input file
Open succeeded on output file
```

## <a name="see-also"></a>参照

[下位入出力](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod、_wchmod](chmod-wchmod.md)<br/>
[_close](close.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_dup、_dup2](dup-dup2.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[_sopen、_wsopen](sopen-wsopen.md)<br/>
