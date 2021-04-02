---
description: '詳細については、次を参照してください: _umask_s'
title: _umask_s
ms.date: 4/2/2020
api_name:
- _umask_s
- _o__umask_s
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
- unmask_s
- _umask_s
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
ms.openlocfilehash: 8a87d924073d5e13d8c5ce0377276cf10a9e0798
ms.sourcegitcommit: 82a0d23b04d0776c00209d885689cbc5be36d3b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "106099314"
---
# <a name="_umask_s"></a>_umask_s

既定のファイル アクセス許可マスクを設定します。 「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) の説明にあるとおり、セキュリティが強化されたバージョンの [_umask](umask.md) です。

## <a name="syntax"></a>構文

```C
errno_t _umask_s(
   int mode,
   int * pOldMode
);
```

### <a name="parameters"></a>パラメーター

*mode*<br/>
既定のアクセス許可の設定。

*pOldMode*<br/>
アクセス許可設定の以前の値。

## <a name="return-value"></a>戻り値

*モード* で有効なモードが指定されていない場合、または *poldmode* ポインターが **NULL** の場合は、エラーコードを返します。

### <a name="error-conditions"></a>エラー条件

|*mode*|*pOldMode*|戻り値|*Poldmode* の内容|
|------------|----------------|----------------------|--------------------------------|
|any|**NULL**|**EINVAL**|変更されない|
|無効なモード|any|**EINVAL**|変更されない|

上記のいずれかの条件が発生すると、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラ―が呼び出されます。 実行の継続が許可された場合、 **_umask_s** は **einval** を返し、 **errno** を **einval** に設定します。

## <a name="remarks"></a>解説

**_Umask_s** 関数は、現在のプロセスのファイルアクセス許可マスクを *モード* によって指定されたモードに設定します。 ファイルのアクセス許可マスクは、 **_creat**、 **_open**、または **_sopen** によって作成された新しいファイルのアクセス許可の設定を変更します。 マスクのビットが 1 の場合は、ファイルの要求されたアクセス許可値に対応するビットは 0 (許可しない) に設定されます。 マスクのビットが 0 の場合は、対応するビットは変更されません。 新しいファイルのアクセス許可の設定は、そのファイルが最初に閉じられるまで、設定されません。

整数式 *pmode* には、sysstatで定義されている次のマニフェスト定数のいずれかまたは両方が含まれています。始め

|*pmode*|説明|
|-|-|
|**_S_IWRITE**|書き込みが許可されます。|
|**_S_IREAD**|読み取りが許可されます。|
|**_S_IREAD** \|**_S_IWRITE**|読み取りと書き込みが許可されます。|

両方の定数が指定されている場合は、ビットごとの OR 演算子 () と結合され **|** ます。 *モード* 引数が **_S_IREAD** の場合、読み取りは許可されません (ファイルは書き込み専用です)。 *モード* 引数が **_S_IWRITE** の場合、書き込みは許可されません (ファイルは読み取り専用です)。 たとえば、マスクに書き込みビットが設定されている場合、新しいファイルはいずれも読み取り専用となります。 MS-DOS および Windows オペレーティング システムでは、すべてのファイルは読み取り可能です。書き込み専用のアクセス許可を与えることはできません。 このため、読み取りビットを **_umask_s** に設定しても、ファイルのモードには影響しません。

*Pmode* がマニフェスト定数のいずれかの組み合わせではない場合、または別の定数セットを組み込んでいる場合、関数は単にそれらを無視します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_umask_s**|\<io.h>および \<sys/stat.h>\<sys/types.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_umask_s.c
/* This program uses _umask_s to set
* the file-permission mask so that all future
* files will be created as read-only files.
* It also displays the old mask.
*/

#include <sys/stat.h>
#include <sys/types.h>
#include <io.h>
#include <stdio.h>

int main( void )
{
   int oldmask, err;

   /* Create read-only files: */
   err = _umask_s( _S_IWRITE, &oldmask );
   if (err)
   {
      printf("Error setting the umask.\n");
      exit(1);
   }
   printf( "Oldmask = 0x%.4x\n", oldmask );
}
```

```Output
Oldmask = 0x0000
```

## <a name="see-also"></a>関連項目

[ファイルの処理](../../c-runtime-library/file-handling.md)<br/>
[低レベル i/o](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod、_wchmod](chmod-wchmod.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_mkdir、_wmkdir](mkdir-wmkdir.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_umask](umask.md)<br/>
