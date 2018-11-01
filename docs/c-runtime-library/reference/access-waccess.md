---
title: _access、_waccess
ms.date: 11/04/2016
apiname:
- _access
- _waccess
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
- _waccess
- _access
- taccess
- waccess
- _taccess
helpviewer_keywords:
- access function
- _taccess function
- waccess function
- _access function
- _waccess function
- taccess function
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
ms.openlocfilehash: 87ac912ab47483929b3afc2357331f8d97264b31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565478"
---
# <a name="access-waccess"></a>_access、_waccess

ファイルが読み取り専用かどうかを判断します。 セキュリティを強化したバージョンを使用できます。「[_access_s、_waccess_s](access-s-waccess-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
int _access(
   const char *path,
   int mode
);
int _waccess(
   const wchar_t *path,
   int mode
);
```

### <a name="parameters"></a>パラメーター

*path*<br/>
ファイルまたはディレクトリ パス。

*モード*<br/>
読み取り/書き込み属性。

## <a name="return-value"></a>戻り値

ファイルに特定のモードが設定されている場合、各関数は 0 を返します。 名前付きのファイルが存在しないか、特定のモードがない場合は-1 を返しますこの場合、`errno`に次の表に示すように設定します。

|||
|-|-|
`EACCES`|アクセス拒否: ファイルのアクセス許可の設定では、指定したアクセスは許可されません。
`ENOENT`|ファイル名またはパスが見つかりません。
`EINVAL`|無効なパラメーター。

リターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>Remarks

ファイルを使用すると、 **_access**関数は、指定したファイルまたはディレクトリが存在しの値で指定された属性を持つかどうかを決定します。*モード*します。 ディレクトリを使用すると **_access**だけを指定したディレクトリが存在するかどうか判断します。 Windows 2000 以降のオペレーティング システムを保存のすべてのディレクトリの読み取りおよび書き込みアクセス。

|*モード*値|ファイル チェックの目的|
|------------------|---------------------|
|00|存在のみ|
|02|書き込み専用|
|04|読み取り専用|
|06|読み取りおよび書き込み|

この関数は、ファイルとディレクトリが読み取り専用かどうかだけを確認し、ファイルシステムのセキュリティ設定は確認しません。 そのためには、アクセス トークンが必要です。 ファイルシステムのセキュリティの詳細については、「[アクセス トークン](/windows/desktop/SecAuthZ/access-tokens)」を参照してください。 ATL クラスはこの機能を提供するために存在します。「[CAccessToken クラス](../../atl/reference/caccesstoken-class.md)」を参照してください。

**_waccess**のワイド文字バージョンです **_access**、*パス*への引数 **_waccess**はワイド文字列です。 **_waccess**と **_access**動作は同じです。

この関数は、パラメーターを検証します。 場合*パス*null または*モード*有効なモードを指定しない」の説明に従って、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、-1 を返します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_taccess`|**_access**|**_access**|**_waccess**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**_access**|\<io.h>|\<errno.h>|
|**_waccess**|\<wchar.h> または \<io.h>|\<errno.h>|

## <a name="example"></a>例

次の例では **_access**はという名前のファイルを確認します。C が存在するかどうかと、書き込みが許可されているかどうかを確認します。

```C
// crt_access.c
// compile with: /W1
// This example uses _access to check the file named
// crt_ACCESS.C to see if it exists and if writing is allowed.

#include  <io.h>
#include  <stdio.h>
#include  <stdlib.h>

int main( void )
{
    // Check for existence.
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )
    {
        printf_s( "File crt_ACCESS.C exists.\n" );

        // Check for write permission.
        // Assume file is read-only.
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );
    }
}
```

```Output
File crt_ACCESS.C exists.
File crt_ACCESS.C does not have write permission.
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_chmod、_wchmod](chmod-wchmod.md)<br/>
[_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_stat、_wstat 関数](stat-functions.md)