---
description: '詳細については、次を参照してください: _chdir、_wchdir'
title: _chdir、_wchdir
ms.date: 4/2/2020
api_name:
- _wchdir
- _chdir
- _o__chdir
- _o__wchdir
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
- tchdir
- _chdir
- _wchdir
- _tchdir
- wchdir
helpviewer_keywords:
- _tchdir function
- _chdir function
- _wchdir function
- tchdir function
- wchdir function
- chdir function
- directories [C++], changing
ms.assetid: 85e9393b-62ac-45d5-ab2a-fa2217f6152e
ms.openlocfilehash: 190e9d6445417aed8c35843cb4c386d49535ebbd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186715"
---
# <a name="_chdir-_wchdir"></a>_chdir、_wchdir

現在の作業ディレクトリを変更します。

## <a name="syntax"></a>構文

```C
int _chdir(
   const char *dirname
);
int _wchdir(
   const wchar_t *dirname
);
```

### <a name="parameters"></a>パラメーター

*dirname*<br/>
新しい作業ディレクトリのパス。

## <a name="return-value"></a>戻り値

これらの関数は、成功した場合、値 0 を返します。 戻り値-1 はエラーを示します。 指定されたパスが見つからなかった場合、 **errno** は **ENOENT** に設定されます。 *Dirname* が **NULL** の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、 **errno** は **EINVAL** に設定され、この関数は-1 を返します。

## <a name="remarks"></a>解説

**_Chdir** 関数は、現在の作業ディレクトリを *dirname* によって指定されたディレクトリに変更します。 *Dirname* パラメーターは既存のディレクトリを参照する必要があります。 この関数は、任意のドライブの現在の作業ディレクトリを変更できます。 新しいドライブ文字が *dirname* に指定されている場合は、既定のドライブ文字も同様に変更されます。 たとえば、A が既定のドライブ文字で、\BIN が現在の作業ディレクトリの場合、次の呼び出しにより、ドライブ C の現在の作業ディレクトリが変更され、C が新しい既定のドライブとして設定されます。

```C
_chdir("c:\temp");
```

パスに省略可能な円記号 (**&#92;**) を使用する場合は、1つの円記号 (**&#92;**) を表すために、C 文字列リテラルに2つの円記号 (**&#92;&#92;**) を配置する必要があります。

**_wchdir** は **_chdir** のワイド文字バージョンです。**_wchdir** の *dirname* 引数は、ワイド文字列です。 **_wchdir** と **_chdir** は同じように動作します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mapping"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchdir**|**_chdir**|**_chdir**|**_wchdir**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_chdir**|\<direct.h>|\<errno.h>|
|**_wchdir**|\<direct.h> または \<wchar.h>|\<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_chdir.c
// arguments: C:\WINDOWS

/* This program uses the _chdir function to verify
   that a given directory exists. */

#include <direct.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( int argc, char *argv[] )
{

   if(_chdir( argv[1] ) )
   {
      switch (errno)
      {
      case ENOENT:
         printf( "Unable to locate the directory: %s\n", argv[1] );
         break;
      case EINVAL:
         printf( "Invalid buffer.\n");
         break;
      default:
         printf( "Unknown error.\n");
      }
   }
   else
      system( "dir *.exe");
}
```

```Output
Volume in drive C has no label.
Volume Serial Number is 2018-08A1

Directory of c:\windows

08/29/2002  04:00 AM         1,004,032 explorer.exe
12/17/2002  04:43 PM            10,752 hh.exe
03/03/2003  09:24 AM            33,792 ieuninst.exe
10/29/1998  04:45 PM           306,688 IsUninst.exe
08/29/2002  04:00 AM            66,048 NOTEPAD.EXE
03/03/2003  09:24 AM            33,792 Q330994.exe
08/29/2002  04:00 AM           134,144 regedit.exe
02/28/2003  06:26 PM            46,352 setdebug.exe
08/29/2002  04:00 AM            15,360 TASKMAN.EXE
08/29/2002  04:00 AM            49,680 twunk_16.exe
08/29/2002  04:00 AM            25,600 twunk_32.exe
08/29/2002  04:00 AM           256,192 winhelp.exe
08/29/2002  04:00 AM           266,752 winhlp32.exe
              13 File(s)      2,249,184 bytes
               0 Dir(s)  67,326,029,824 bytes free
```

## <a name="see-also"></a>関連項目

[ディレクトリコントロール](../../c-runtime-library/directory-control.md)<br/>
[_mkdir、_wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir、_wrmdir](rmdir-wrmdir.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
