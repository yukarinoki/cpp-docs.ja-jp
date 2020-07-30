---
title: _write
ms.date: 4/2/2020
api_name:
- _write
- _o__write
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _write
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
ms.openlocfilehash: 02864a797a64e6c1b1d836edf4e435cdb43d0932
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211620"
---
# <a name="_write"></a>_write

ファイルにデータを書き込みます。

## <a name="syntax"></a>構文

```C
int _write(
   int fd,
   const void *buffer,
   unsigned int count
);
```

### <a name="parameters"></a>パラメーター

*スクリプター*<br/>
データを書き込むファイルのファイル記述子。

*格納*<br/>
書き込むデータ。

*count*<br/>
バイト数。

## <a name="return-value"></a>戻り値

成功した場合、 **_write**は書き込まれたバイト数を返します。 ディスク上に残っている実際の領域が、関数がディスクに書き込もうとしているバッファーのサイズよりも小さい場合、 **_write**は失敗し、バッファーの内容はディスクにフラッシュされません。 戻り値-1 はエラーを示します。 無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、この関数は-1 を返し、 **errno**は3つの値のいずれかに設定され**ます。これは、ファイル**記述子が無効であるか、ファイルが書き込み用に開かれていないことを意味します。**ENOSPC**。これは、操作に必要な領域がデバイスに残っていないことを意味します。または**EINVAL**。*バッファー*が null ポインターであるか、また*は奇数のバイト数が*Unicode モードでファイルに書き込まれるように渡されたことを示します。

これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

ファイルがテキストモードで開かれている場合、各ラインフィード文字は出力のキャリッジリターンラインフィードのペアで置き換えられます。 置換は戻り値には影響しません。

ファイルが Unicode 変換モードで開かれている場合 (たとえば、 *fd*が **_open**または **_sopen**を使用して開かれ、 **_O_WTEXT**を含むモードパラメーターを使用して起動された場合)。 **_O_U16TEXT**、または **_O_U8TEXT**。 **fopen**を使用して開いた場合、または、 **ccs = unicode**、 **ccs = 16LE**、または**ccs = utf-8**を含むモードパラメーターを使用して開かれている場合、またはモードが **_setmode**を使用して unicode 変換モードに変更された場合、*バッファー*は **`wchar_t`** **utf-16**データを含むの配列へのポインターとして解釈さ このモードで奇数バイトの書き込みを試みると、パラメーター検証エラーが発生します。

## <a name="remarks"></a>解説

**_Write**関数は、*バッファー*のバイト*数*を*fd*に関連付けられたファイルに書き込みます。 書き込み操作は、指定されたファイルに関連付けられたファイル ポインター (存在する場合) の現在の位置で開始されます。 ファイルが追加用に開かれている場合、操作はファイルの現在の末尾で開始されます。 書き込み操作の後、ファイルポインターは、書き込まれたバイト数だけ増加します。

テキストモードで開かれたファイルに書き込む場合、 **_write**は CTRL + Z 文字をファイルの論理終端として扱います。 デバイスに書き込む場合、 **_write**はバッファー内の CTRL + Z 文字を出力ターミネータとして扱います。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_write**|\<io.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt__write.c
//
// This program opens a file for output and uses _write to write
// some bytes to the file.

#include <io.h>
#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <errno.h>
#include <share.h>

char buffer[] = "This is a test of '_write' function";

int main( void )
{
   int         fileHandle = 0;
   unsigned    bytesWritten = 0;

   if ( _sopen_s(&fileHandle, "write.o", _O_RDWR | _O_CREAT,
                  _SH_DENYNO, _S_IREAD | _S_IWRITE) )
      return -1;

   if (( bytesWritten = _write( fileHandle, buffer, sizeof( buffer ))) == -1 )
   {
      switch(errno)
      {
         case EBADF:
            perror("Bad file descriptor!");
            break;
         case ENOSPC:
            perror("No space left on device!");
            break;
         case EINVAL:
            perror("Invalid parameter: buffer was NULL!");
            break;
         default:
            // An unrelated error occurred
            perror("Unexpected error!");
      }
   }
   else
   {
      printf_s( "Wrote %u bytes to file.\n", bytesWritten );
   }
   _close( fileHandle );
}
```

```Output
Wrote 36 bytes to file.
```

## <a name="see-also"></a>関連項目

[低レベル i/o](../../c-runtime-library/low-level-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_setmode](setmode.md)<br/>
