---
title: _umask_s
ms.date: 11/04/2016
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
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
ms.openlocfilehash: 878a22cb2884c36e792ff8dead1453582addb5b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62268915"
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

場合、エラー コードを返します*モード*で有効なモードが指定されていない、または*pOldMode*ポインターが**NULL**します。

### <a name="error-conditions"></a>エラー条件

|*モード*|*pOldMode*|戻り値|内容*pOldMode*|
|------------|----------------|----------------------|--------------------------------|
|任意|**NULL**|**EINVAL**|変更されない|
|無効なモード|任意|**EINVAL**|変更されない|

上記のいずれかの条件が発生すると、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラ―が呼び出されます。 続けるには、実行が許可された場合 **_umask_s**返します**EINVAL**設定と**errno**に**EINVAL**します。

## <a name="remarks"></a>Remarks

**_Umask_s**関数では、現在のプロセスのファイルのアクセス許可マスクを設定で指定されたモードに*モード*します。 ファイルのアクセス許可マスクは、新しく作成したファイルのアクセス許可の設定を変更します。 **_creat**、 **_open**、または **_sopen**します。 マスクのビットが 1 の場合は、ファイルの要求されたアクセス許可値に対応するビットは 0 (許可しない) に設定されます。 マスクのビットが 0 の場合は、対応するビットは変更されません。 新しいファイルのアクセス許可の設定は、そのファイルが最初に閉じられるまで、設定されません。

整数式*pmode* SYS\STAT で定義されている、次のマニフェスト定数の一方または両方が含まれています。H:

|*pmode*||
|-|-|
|**_S_IWRITE**|書き込みが許可されます。|
|**_S_IREAD**|読み取りが許可されます。|
|**_S_IREAD** \| **_S_IWRITE**|読み取りと書き込みが許可されます。|

ビットごとの OR 演算子で参加している両方の定数を指定する場合 ( **|** )。 場合、*モード*引数が **_S_IREAD**読み取りが許可されていません (ファイルは書き込み専用)。 場合、*モード*引数が **_S_IWRITE**書き込みが許可されていません (ファイルは読み取り専用)。 たとえば、マスクに書き込みビットが設定されている場合、新しいファイルはいずれも読み取り専用となります。 MS-DOS および Windows オペレーティング システムでは、すべてのファイルは読み取り可能です。書き込み専用のアクセス許可を与えることはできません。 そのため、読み取りのビットを設定 **_umask_s**ファイルのモードに影響を与えません。

場合*pmode*マニフェスト定数のいずれかの組み合わせではないまたは代替のセットを組み込んで、定数の関数は単にそれらを無視します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
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
