---
title: _umask | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _umask
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
- _umask
dev_langs:
- C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask function
- masks
- umask function
- file permissions [C++]
- files [C++], permission settings for
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce3053bfb19cc81dff15d41d1b5bc6d405da619f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412617"
---
# <a name="umask"></a>_umask

既定のファイル アクセス許可マスクを設定します。 この関数のセキュリティが強化されたバージョンについては、「[_umask_s](umask-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
int _umask( int pmode );
```

### <a name="parameters"></a>パラメーター

*pmode*<br/>
既定のアクセス許可の設定。

## <a name="return-value"></a>戻り値

**_umask**の前の値を返します*pmode*です。 エラーの戻り値はありません。

## <a name="remarks"></a>コメント

**_Umask**関数では、現在のプロセスのファイルのアクセス許可マスクを設定で指定されたモードに*pmode*です。 ファイルのアクセス許可マスクを新しく作成したファイルのアクセス許可の設定を変更 **_creat**、 **_open**、または **_sopen**です。 マスクのビットが 1 の場合は、ファイルの要求されたアクセス許可値に対応するビットは 0 (許可しない) に設定されます。 マスクのビットが 0 の場合は、対応するビットは変更されません。 新しいファイルのアクセス許可の設定は、そのファイルが最初に閉じられるまで、設定されません。

整数型の式*pmode* SYS\STAT で定義されている、次のマニフェスト定数の一方または両方が含まれています。H:

|*pmode*||
|-|-|
**_S_IWRITE**|書き込みが許可されます。
**_S_IREAD**|読み取りが許可されます。
**_S_IREAD** \| **_S_IWRITE**|読み取りと書き込みが許可されます。

これらはビットごとの OR 演算子で結合両方の定数を指定する場合 ( **|** )。 場合、 *pmode*引数は **_S_IREAD**読み取りが許可されていません (ファイルは書き込み専用)。 場合、 *pmode*引数は **_S_IWRITE**書き込みが許可されていません (ファイルは読み取り専用)。 たとえば、マスクに書き込みビットが設定されている場合、新しいファイルはいずれも読み取り専用となります。 MS-DOS および Windows オペレーティング システムでは、すべてのファイルは読み取り可能です。書き込み専用のアクセス許可を与えることはできません。 したがって、読み取りとビットを設定 **_umask**ファイルのモードにも何も起こりません。

場合*pmode*のマニフェスト定数のいずれかの組み合わせではありませんか、別のセットが組み込まれており、定数の関数は無視されるものです。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_umask**|\<io.h>、\<sys/stat.h>、\<sys/types.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_umask.c
// compile with: /W3
// This program uses _umask to set
// the file-permission mask so that all future
// files will be created as read-only files.
// It also displays the old mask.
#include <sys/stat.h>
#include <sys/types.h>
#include <io.h>
#include <stdio.h>

int main( void )
{
   int oldmask;

   /* Create read-only files: */
   oldmask = _umask( _S_IWRITE ); // C4996
   // Note: _umask is deprecated; consider using _umask_s instead
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
