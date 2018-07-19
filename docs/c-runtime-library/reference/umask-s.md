---
title: _umask_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _umask_s
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
- unmask_s
- _umask_s
dev_langs:
- C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d45cb3ded6fd2c3d7a380069a7d7f3fd79619810
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32414481"
---
# <a name="umasks"></a>_umask_s

既定のファイル アクセス許可マスクを設定します。 「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) の説明にあるとおり、セキュリティが強化されたバージョンの [_umask](umask.md) です。

## <a name="syntax"></a>構文

```C
errno_t _umask_s(
   int mode,
   int * pOldMode
);
```

### <a name="parameters"></a>パラメーター

*モード*<br/>
既定のアクセス許可の設定。

*pOldMode*<br/>
アクセス許可設定の以前の値。

## <a name="return-value"></a>戻り値

場合、エラー コードを返します*モード*有効なモードで指定されていない、または*pOldMode*ポインターが**NULL**です。

### <a name="error-conditions"></a>エラー条件

|*モード*|*pOldMode*|戻り値|内容*pOldMode*|
|------------|----------------|----------------------|--------------------------------|
|任意|**NULL**|**EINVAL**|変更されない|
|無効なモード|任意|**EINVAL**|変更されない|

上記のいずれかの条件が発生すると、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラ―が呼び出されます。 続けるには、実行が許可された場合 **_umask_s**返します**EINVAL**設定と**errno**に**EINVAL**です。

## <a name="remarks"></a>コメント

**_Umask_s**関数では、現在のプロセスのファイルのアクセス許可マスクを設定で指定されたモードに*モード*です。 ファイルのアクセス許可マスクを新しく作成したファイルのアクセス許可の設定を変更 **_creat**、 **_open**、または **_sopen**です。 マスクのビットが 1 の場合は、ファイルの要求されたアクセス許可値に対応するビットは 0 (許可しない) に設定されます。 マスクのビットが 0 の場合は、対応するビットは変更されません。 新しいファイルのアクセス許可の設定は、そのファイルが最初に閉じられるまで、設定されません。

整数型の式*pmode* SYS\STAT で定義されている、次のマニフェスト定数の一方または両方が含まれています。H:

|*pmode*||
|-|-|
|**_S_IWRITE**|書き込みが許可されます。|
|**_S_IREAD**|読み取りが許可されます。|
|**_S_IREAD** \| **_S_IWRITE**|読み取りと書き込みが許可されます。|

これらはビットごとの OR 演算子で結合両方の定数を指定する場合 ( **|** )。 場合、*モード*引数は **_S_IREAD**読み取りが許可されていません (ファイルは書き込み専用)。 場合、*モード*引数は **_S_IWRITE**書き込みが許可されていません (ファイルは読み取り専用)。 たとえば、マスクに書き込みビットが設定されている場合、新しいファイルはいずれも読み取り専用となります。 MS-DOS および Windows オペレーティング システムでは、すべてのファイルは読み取り可能です。書き込み専用のアクセス許可を与えることはできません。 したがって、読み取りとビットを設定 **_umask_s**ファイルのモードにも何も起こりません。

場合*pmode*のマニフェスト定数のいずれかの組み合わせではありませんか、別のセットが組み込まれており、定数の関数は無視されるものです。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_umask_s**|\<io.h> と \<sys/stat.h> と \<sys/types.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[下位入出力](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod、_wchmod](chmod-wchmod.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_mkdir、_wmkdir](mkdir-wmkdir.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_umask](umask.md)<br/>
