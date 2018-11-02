---
title: _write
ms.date: 11/04/2016
apiname:
- _write
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
- _write
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
ms.openlocfilehash: b3fa53b21d4ea23c5f8e59de673f4074deedb505
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519250"
---
# <a name="write"></a>_write

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

*fd*<br/>
データを書き込むファイルのファイル記述子。

*バッファー*<br/>
書き込むデータ。

*count*<br/>
バイト数。

## <a name="return-value"></a>戻り値

成功した場合、 **_write**実際に書き込まれたバイト数を返します。 ディスクに残っている実際の領域が、関数が、ディスクに書き込むしようとしたバッファーのサイズより小さい場合 **_write**が失敗し、バッファーの内容をディスクにフラッシュしません。 戻り値-1 はエラーを示します。 無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、関数は-1 を返しますと**errno** 3 つの値のいずれかに設定されている: **EBADF**、つまり、ファイル記述子が正しくないか、ファイルが書き込み用に開かれていません。**ENOSPC**、十分な空き領域が残って操作については、デバイスがないことを意味または**EINVAL**、つまり*バッファー*が null ポインターかを奇数*カウント*Unicode モードでのファイルに書き込まれるバイトが渡されました。

これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

テキスト モードで、ファイルを開く場合は、それぞれのラインフィード文字がキャリッジ リターン - ライン フィードのペアで、出力に置き換えられます。 この置き換えは、戻り値には影響しません。

Unicode 変換モードでファイルを開いたときに、たとえば場合、 *fd*を使用して、開く**開く (_o)** または **_sopen**とを含むモード パラメーター **_O_WTEXT**、 **_O_U16TEXT**、または **_O_U8TEXT**を使用して開かれた場合、または**fopen**とを含むモード パラメーター **ccs =UNICODE**、 **ccs = UTF 16LE**、または**ccs = utf-8**を使用して、モードが Unicode 変換モードに変更された場合または **_setmode**—*バッファー*の配列へのポインターとして解釈される**wchar_t**を格納している**utf-16**データ。 このモードで奇数バイトの書き込みを試みると、パラメーター検証エラーが発生します。

## <a name="remarks"></a>Remarks

**_Write**関数*カウント*からバイト*バッファー*に関連付けられているファイルに*fd*します。 書き込み操作は、指定されたファイルに関連付けられたファイル ポインター (存在する場合) の現在の位置で開始されます。 ファイルが追加用に開かれている場合、操作はファイルの現在の末尾で開始されます。 書き込み操作の後、ファイル ポインターは実際に書き込まれたバイト数の分、増加します。

テキスト モードで開かれたファイルに書き込むときに **_write** CTRL+Z 文字を論理ファイルの終わりとして扱います。 デバイスに書き込むときに **_write**を出力の終端として、バッファー内の CTRL+Z 文字を扱います。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_write**|\<io.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
            // An unrelated error occured
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
