---
title: _access_s、_waccess_s
ms.date: 4/2/2020
api_name:
- _access_s
- _waccess_s
- _o__access_s
- _o__waccess_s
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- waccess_s
- access_s
- _waccess_s
- _access_s
helpviewer_keywords:
- access_s function
- taccess_s function
- _taccess_s function
- waccess_s function
- _access_s function
- _waccess_s function
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
ms.openlocfilehash: 7f16951b99eb29bcb8c39499c29be1018cb86616
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349125"
---
# <a name="_access_s-_waccess_s"></a>_access_s、_waccess_s

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

ファイルに特定のモードが設定されている場合、各関数は 0 を返します。 指定したファイルが存在しないか、特定のモードでアクセスできない場合、関数はエラー コードを返します。 この場合、関数は次のようにエラー コードをセットから返し、`errno` も同じ値に設定します。

|errno の値|条件|
|-|-|
`EACCES`|アクセスが拒否されました。 ファイルのアクセス許可の設定では、指定したアクセスは許可されません。
`ENOENT`|ファイル名またはパスが見つかりません。
`EINVAL`|無効なパラメーター。

詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

ファイルと共に使用すると **、_access_s**関数は、指定されたファイルが存在するかどうか、および*mode*の値で指定されたとおりにアクセスできるかどうかを判別します。 ディレクトリと共に使用 **_access_s、指定**したディレクトリが存在するかどうかを判断します。 Windows 2000 以降のオペレーティング システムでは、すべてのディレクトリに読み取りおよび書き込みアクセス権があります。

|モード値|ファイル チェックの目的|
|----------------|---------------------|
|00|存在のみ|
|02|書き込みアクセス許可|
|04|読み取りアクセス許可|
|06|読み取りおよび書き込みアクセス許可|

ファイルの読み取りおよび書き込みアクセス許可では、ファイルを開く権限を確認するには不十分です。 たとえば、あるファイルが別のプロセスによってロックされている場合 **、_access_s0**を返してもアクセスできない可能性があります。

**_waccess_s**ワイド文字の **_access_s**で **、_waccess_s**への*パス*引数はワイド文字の文字列です。 それ以外**の場合、_waccess_s**と **_access_s**は同じように動作します。

これらの関数では、パラメーターの検証が行われます。 *path*が NULL の場合、または*モード*で有効なモードが指定されていない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_taccess_s`|**_access_s**|**_access_s**|**_waccess_s**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_access_s**|\<io.h>|\<errno.h>|
|**_waccess_s**|\<wchar.h> または \<io.h>|\<errno.h>|

## <a name="example"></a>例

この例では **、_access_s**を使用して crt_access_s.c という名前のファイルが存在するかどうか、および書き込みが許可されているかどうかを確認します。

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
[_stat、_wstat 関数](stat-functions.md)
