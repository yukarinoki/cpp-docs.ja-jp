---
title: _isatty
ms.date: 11/04/2016
apiname:
- _isatty
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _isatty
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
ms.openlocfilehash: ef0df5f859779c081df47ef4bfe938ec2601d524
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157475"
---
# <a name="isatty"></a>_isatty

ファイル記述子が文字デバイスに関連付けられているかどうかを判定します。

## <a name="syntax"></a>構文

```C
int _isatty( int fd );
```

### <a name="parameters"></a>パラメーター

*fd*<br/>
調べるデバイスを参照するファイル記述子。

## <a name="return-value"></a>戻り値

**_isatty**記述子がキャラクター デバイスに関連付けられている場合は 0 以外の値を返します。 それ以外の場合、 **_isatty** 0 を返します。

## <a name="remarks"></a>Remarks

**_Isatty**関数は決定かどうか*fd*キャラクター デバイス (端末、コンソール、プリンター、またはシリアル ポート) に関連付けられています。

この関数は、検証、 *fd*パラメーター。 場合*fd* 、不適切なファイル ポインターで説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続、関数の戻り値 0 とセットが許可された場合**errno**に**EBADF**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_isatty**|\<io.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_isatty.c
/* This program checks to see whether
* stdout has been redirected to a file.
*/

#include <stdio.h>
#include <io.h>

int main( void )
{
   if( _isatty( _fileno( stdout ) ) )
      printf( "stdout has not been redirected to a file\n" );
   else
      printf( "stdout has been redirected to a file\n");
}
```

### <a name="sample-output"></a>出力例

```Output
stdout has not been redirected to a file
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
