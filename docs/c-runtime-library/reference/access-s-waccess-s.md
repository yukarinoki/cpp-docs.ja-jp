---
title: _access_s、_waccess_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _access_s
- _waccess_s
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
- waccess_s
- access_s
- _waccess_s
- _access_s
dev_langs:
- C++
helpviewer_keywords:
- access_s function
- taccess_s function
- _taccess_s function
- waccess_s function
- _access_s function
- _waccess_s function
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24c269951eacfc2f7a5d40c8fad1e4fb67cc1d2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392092"
---
# <a name="accesss-waccesss"></a>_access_s、_waccess_s

ファイルの読み取り/書き込みアクセス許可を決定します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_access, _waccess](access-waccess.md) です。

## <a name="syntax"></a>構文

```C
errno_t _access_s(
   const char *path,
   int mode
);
errno_t _waccess_s(
   const wchar_t *path,
   int mode
);
```

### <a name="parameters"></a>パラメーター

*path*<br/>
ファイルまたはディレクトリ パス。

*モード*<br/>
アクセス許可の設定。

## <a name="return-value"></a>戻り値

ファイルに特定のモードが設定されている場合、各関数は 0 を返します。 指定したファイルが存在しないか、特定のモードでアクセスできない場合、関数はエラー コードを返します。 この場合、関数の次のように、セットからエラー コードを返しも設定**errno**同じ値にします。

|errno の値|条件|
|-|-|
**EACCES**|アクセスが拒否されました。 ファイルのアクセス許可の設定では、指定したアクセスは許可されません。
**ENOENT**|ファイル名またはパスが見つかりません。
**EINVAL**|無効なパラメーター。

詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

ファイルを使用すると、 **_access_s**関数は、指定したファイルが存在し、としてアクセスできるかどうかを判断の値で指定された*モード*です。 ディレクトリを使用すると **_access_s**のみに指定されたディレクトリが存在するかどうかを判断します。 Windows 2000 以降のオペレーティング システムでは、すべてのディレクトリは読み取りおよび書き込みアクセス。

|モード値|ファイル チェックの目的|
|----------------|---------------------|
|00|存在のみ|
|02|書き込みアクセス許可|
|04|読み取りアクセス許可|
|06|読み取りおよび書き込みアクセス許可|

ファイルの読み取りおよび書き込みアクセス許可では、ファイルを開く権限を確認するには不十分です。 たとえば、ファイルが別のプロセスによってロックされている場合にできない可能性がありますアクセス可能な場合でも **_access_s** 0 を返します。

**_waccess_s**のワイド文字バージョンは、 **_access_s**ここで、*パス*引数 **_waccess_s**ワイド文字列です。 それ以外の場合、 **_waccess_s**と **_access_s**動作は同じです。

これらの関数では、パラメーターの検証が行われます。 場合*パス*は**NULL**または*モード*有効なモードが指定されていません」の説明に従って、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md). 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**返す**EINVAL**です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_taccess_s**|**_access_s**|**_access_s**|**_waccess_s**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_access_s**|\<io.h>|\<errno.h>|
|**_waccess_s**|\<wchar.h> または \<io.h>|\<errno.h>|

## <a name="example"></a>例

この例では **_access_s**をという名前のファイルが存在するかどうかと書き込みが許可されているかどうかを表示する crt_access_s.c を確認します。

```C
// crt_access_s.c

#include <io.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
    errno_t err = 0;

    // Check for existence.
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )
    {
        printf_s( "File crt_access_s.c exists.\n" );

        // Check for write permission.
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )
        {
            printf_s( "File crt_access_s.c does have "
                      "write permission.\n" );
        }
        else
        {
            printf_s( "File crt_access_s.c does not have "
                      "write permission.\n" );
        }
    }
    else
    {
        printf_s( "File crt_access_s.c does not exist.\n" );
    }
}
```

```Output
File crt_access_s.c exists.
File crt_access_s.c does not have write permission.
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_access、_waccess](access-waccess.md)<br/>
[_chmod、_wchmod](chmod-wchmod.md)<br/>
[_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_stat、_wstat 関数](stat-functions.md)<br/>
