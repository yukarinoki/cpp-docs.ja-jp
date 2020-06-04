---
title: _chmod、_wchmod
ms.date: 4/2/2020
api_name:
- _chmod
- _wchmod
- _o__chmod
- _o__wchmod
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _chmod
- _wchmod
- wchmod
helpviewer_keywords:
- _chmod function
- wchmod function
- file permissions [C++]
- chmod function
- files [C++], changing permissions
- _wchmod function
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
ms.openlocfilehash: b1bc89ce51fff44a847111d68cac8e8b3f58a635
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917010"
---
# <a name="_chmod-_wchmod"></a>_chmod、_wchmod

ファイルのアクセス許可の設定を変更します。

## <a name="syntax"></a>構文

```C
int _chmod( const char *filename, int pmode );
int _wchmod( const wchar_t *filename, int pmode );
```

### <a name="parameters"></a>パラメーター

*/db*<br/>
既存のファイルの名前。

*pmode*<br/>
ファイルのアクセス許可の設定。

## <a name="return-value"></a>戻り値

これらの関数は、アクセス許可の設定が正常に変更された場合に 0 を返します。 戻り値-1 はエラーを示します。 指定したファイルが見つからなかった場合、 **errno**は**ENOENT**に設定されます。パラメーターが無効な場合、 **errno**は**EINVAL**に設定されます。

## <a name="remarks"></a>解説

**_Chmod**関数は、 *filename*によって指定されたファイルのアクセス許可の設定を変更します。 アクセス許可の設定は、ファイルに対する読み取りと書き込みのアクセスを制御します。 整数式*pmode*には、sysh に定義されている次のマニフェスト定数のいずれかまたは両方が含まれています。

| *pmode* | 説明 |
|-|-|
| **\_S\_IREAD** | 読み取りのみが許可されます。 |
| **\_S\_IWRITE** | 書き込みが許可されます。 (実際には、読み取りと書き込みが許可されます)。 |
| **\_S\_iread** &#124; ** \_s\_iread** | 読み取りと書き込みが許可されます。 |

両方の定数が指定されている場合は、ビットごとの**\|** or 演算子 () と結合されます。 書き込みアクセス許可が与えられない場合、ファイルは読み取り専用になります。 ファイルはすべて常に読み取り可能です。書き込みのみのアクセス許可を与えることはできません。 したがって、 **_S_IWRITE**と **_S_IREAD** \| **_S_IWRITE**のモードは同等です。

**_wchmod**は **_chmod**のワイド文字バージョンです。**_wchmod**する*filename*引数は、ワイド文字列です。 **_wchmod**と **_chmod**は同じように動作します。

この関数は、パラメーターを検証します。 *Pmode*がマニフェスト定数のいずれかの組み合わせではない場合、または別の定数セットを組み込んでいる場合、関数は単にそれらを無視します。 *Filename*が**NULL**の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、 **errno**は**EINVAL**に設定され、この関数は-1 を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchmod**|**_chmod**|**_chmod**|**_wchmod**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_chmod**|\<io.h>|\<sys/types.h>、\<sys/stat.h>、\<errno.h>|
|**_wchmod**|\<io.h> または \<wchar.h>|\<sys/types.h>、\<sys/stat.h>、\<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_chmod.c
// This program uses _chmod to
// change the mode of a file to read-only.
// It then attempts to modify the file.
//

#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

// Change the mode and report error or success
void set_mode_and_report(char * filename, int mask)
{
   // Check for failure
   if( _chmod( filename, mask ) == -1 )
   {
      // Determine cause of failure and report.
      switch (errno)
      {
         case EINVAL:
            fprintf( stderr, "Invalid parameter to chmod.\n");
            break;
         case ENOENT:
            fprintf( stderr, "File %s not found\n", filename );
            break;
         default:
            // Should never be reached
            fprintf( stderr, "Unexpected error in chmod.\n" );
       }
   }
   else
   {
      if (mask == _S_IREAD)
        printf( "Mode set to read-only\n" );
      else if (mask & _S_IWRITE)
        printf( "Mode set to read/write\n" );
   }
   fflush(stderr);
}

int main( void )
{

   // Create or append to a file.
   system( "echo /* End of file */ >> crt_chmod.c_input" );

   // Set file mode to read-only:
   set_mode_and_report("crt_chmod.c_input ", _S_IREAD );

   system( "echo /* End of file */ >> crt_chmod.c_input " );

   // Change back to read/write:
   set_mode_and_report("crt_chmod.c_input ", _S_IWRITE );

   system( "echo /* End of file */ >> crt_chmod.c_input " );
}
```

```Output

A line of text.
```

```Output

      A line of text.Mode set to read-only
Access is denied.
Mode set to read/write
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_access、_waccess](access-waccess.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_stat、_wstat 関数](stat-functions.md)<br/>
