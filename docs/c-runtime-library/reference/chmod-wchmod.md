---
title: _chmod、_wchmod
ms.date: 11/04/2016
apiname:
- _chmod
- _wchmod
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 7f3133aac1548be5cb497fe32ae4f9f1c0e238d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595131"
---
# <a name="chmod-wchmod"></a>_chmod、_wchmod

ファイルのアクセス許可の設定を変更します。

## <a name="syntax"></a>構文

```C
int _chmod( const char *filename, int pmode );
int _wchmod( const wchar_t *filename, int pmode );
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
既存のファイルの名前。

*pmode*<br/>
ファイルのアクセス許可の設定。

## <a name="return-value"></a>戻り値

これらの関数は、アクセス許可の設定が正常に変更された場合に 0 を返します。 戻り値-1 はエラーを示します。 指定したファイルが見つからない場合、 **errno**に設定されている**ENOENT**パラメーターが有効でない場合**errno**に設定されている**EINVAL**します。

## <a name="remarks"></a>Remarks

**_Chmod**関数で指定されたファイルのアクセス許可の設定を変更する*filename*します。 アクセス許可の設定は、ファイルに対する読み取りと書き込みのアクセスを制御します。 整数式*pmode* sys \stat.h で定義されている、次のマニフェスト定数の一方または両方が含まれています。

|*pmode*|説明|
|-|-|
**_S_IREAD**|読み取りのみが許可されます。
**_S_IWRITE**|書き込みが許可されます。 (実際には、読み取りと書き込みが許可されます)。
**_S_IREAD** &AMP;#124; **_S_IWRITE**|読み取りと書き込みが許可されます。

ビットごとに参加している両方の定数が指定されると、or 演算子 (**|**)。 書き込みアクセス許可が与えられない場合、ファイルは読み取り専用になります。 ファイルはすべて常に読み取り可能です。書き込みのみのアクセス許可を与えることはできません。 モードではそのため、 **_S_IWRITE**と **_S_IREAD** | **_S_IWRITE**は同等です。

**_wchmod**のワイド文字バージョンです **_chmod**、 *filename*への引数 **_wchmod**はワイド文字列です。 **_wchmod**と **_chmod**動作は同じです。

この関数は、パラメーターを検証します。 場合*pmode*マニフェスト定数のいずれかの組み合わせではないまたは代替のセットを組み込んで、定数の関数は、単にそれらを無視します。 場合*filename*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL**関数は-1 を返します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchmod**|**_chmod**|**_chmod**|**_wchmod**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_chmod**|\<io.h>|\<sys/types.h>、\<sys/stat.h>、\<errno.h>|
|**_wchmod**|\<io.h> または \<wchar.h>|\<sys/types.h>、\<sys/stat.h>、\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
