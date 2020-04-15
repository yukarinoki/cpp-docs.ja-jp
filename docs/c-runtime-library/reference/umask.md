---
title: _umask
ms.date: 4/2/2020
api_name:
- _umask
- _o__umask
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
- _umask
helpviewer_keywords:
- masks, file-permission-setting
- _umask function
- masks
- umask function
- file permissions [C++]
- files [C++], permission settings for
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
ms.openlocfilehash: b451f979f2925a31f5baaac52351c5d2c0a76da0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362018"
---
# <a name="_umask"></a>_umask

既定のファイル アクセス許可マスクを設定します。 この関数のセキュリティが強化されたバージョンについては、「[_umask_s](umask-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
int _umask( int pmode );
```

### <a name="parameters"></a>パラメーター

*Pmode*<br/>
既定のアクセス許可の設定。

## <a name="return-value"></a>戻り値

**_umask***は、pmode*の前の値を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>解説

**_umask**関数は、現在のプロセスのファイル許可マスクを*pmode*で指定されたモードに設定します。 ファイルアクセス許可マスクは、 **、**_open 、 または **_sopen** **_creat**で作成された新しいファイルのアクセス許可設定を変更します。 マスクのビットが 1 の場合は、ファイルの要求されたアクセス許可値に対応するビットは 0 (許可しない) に設定されます。 マスクのビットが 0 の場合は、対応するビットは変更されません。 新しいファイルのアクセス許可の設定は、そのファイルが最初に閉じられるまで、設定されません。

整数式*pmode*には、SYS\STAT で定義されている次のマニフェスト定数のいずれかまたは両方が含まれています。H：

|*Pmode*| |
|-|-|
| **_S_IWRITE** | 書き込みが許可されます。 |
| **_S_IREAD** | 読み取りが許可されます。 |
| **_S_IREAD&#124;_S_IWRITE** **_S_IWRITE** | 読み取りと書き込みが許可されます。 |

両方の定数が指定されると、ビットごとの OR 演算子 ( **&#124;** ) で結合されます。 *pmode*引数が **_S_IREAD**場合、読み取りは許可されません (ファイルは書き込み専用です)。 *pmode* **引数が**_S_IWRITE の場合、書き込みは許可されません (ファイルは読み取り専用です)。 たとえば、マスクに書き込みビットが設定されている場合、新しいファイルはいずれも読み取り専用となります。 MS-DOS および Windows オペレーティング システムでは、すべてのファイルは読み取り可能です。書き込み専用のアクセス許可を与えることはできません。 したがって、読み取りビットを **_umask**で設定しても、ファイルのモードには影響しません。

*pmode*がマニフェスト定数の組み合わせでない場合、または定数の代替セットが組み込まれていない場合、関数はそれらを無視します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_umask**|\<io.h>、\<sys/stat.h>、\<sys/types.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
