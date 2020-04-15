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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: a616df570d266c335337d897da59a2a0ec69b40e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367390"
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

*Fd*<br/>
データを書き込むファイルのファイル記述子。

*バッファー*<br/>
書き込むデータ。

*count*<br/>
バイト数。

## <a name="return-value"></a>戻り値

成功した場合 **、_write**は書き込まれたバイト数を返します。 ディスクに残っている実際の領域が、関数がディスクに書き込もうとしているバッファのサイズよりも小さい場合 **、_write**失敗し、バッファの内容をディスクにフラッシュしません。 戻り値 -1 はエラーを示します。 無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。 実行が続行できる場合、関数は -1 を返し **、errno**は 3 つの値のいずれかに**設定されます。****ENOSPC**は、操作のためにデバイスに十分なスペースが残っていない、つまり、デバイスに十分なスペースがないことを意味します。**EINVAL**は *、バッファ*がヌル ポインタであったか、または Unicode モードでファイルに書き込まれるように奇数のバイト*数*が渡されたことを意味します。

これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

ファイルがテキスト モードで開かれる場合、各行フィード文字は、出力でキャリッジ リターンと改行のペアに置き換えられます。 置換は戻り値には影響しません。

ファイルが Unicode 変換モードで開かれると、たとえば、次の例を使用します。 *fd*が **_open**または **_sopen**を使用して開き **、_O_WTEXT**、 **_O_U16TEXT**、**または _O_U8TEXT**を含むモード パラメーターを使用して開いた場合、または**fopen**を使用して開き **、ccs=UNICODE、ccs=UTF-16LE、** または**ccs=UTF-8**を含むモード パラメーターを使用して開く場合、または **_setmode***バッファー*を使用してモードが Unicode 変換モードに変更された場合は、utf-16 データを含む**wchar_t**配列へのポインターとして解釈されます。 **ccs=UTF-16LE** **UTF-16** このモードで奇数バイトの書き込みを試みると、パラメーター検証エラーが発生します。

## <a name="remarks"></a>解説

**_write**関数は *、バッファ*から*fd*に関連付けられたファイルに*カウント*バイトを書き込みます。 書き込み操作は、指定されたファイルに関連付けられたファイル ポインター (存在する場合) の現在の位置で開始されます。 ファイルが追加用に開かれている場合、操作はファイルの現在の末尾で開始されます。 書き込み操作の後、ファイル ポインタは書き込まれたバイト数だけ増加します。

テキスト モードで開いたファイルに書き込 **_write、Ctrl** + Z 文字をファイルの論理的な終端として扱います。 デバイスに書き込むとき **、_write**は、バッファ内の Ctrl + Z 文字を出力終端文字として扱います。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
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

[下位入出力](../../c-runtime-library/low-level-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_setmode](setmode.md)<br/>
