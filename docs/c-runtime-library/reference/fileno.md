---
title: _fileno
ms.date: 4/2/2020
api_name:
- _fileno
- _o__fileno
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fileno
helpviewer_keywords:
- file handles [C++], getting from streams
- fileno function
- _fileno function
- streams, getting file handles
ms.assetid: 86474174-2f17-4100-bcc4-352dd976c7b5
ms.openlocfilehash: ec4f08e499efe82b0ee35235e6e2d86dbb9bab66
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346839"
---
# <a name="_fileno"></a>_fileno

ストリームに関連付けられているファイル記述子を取得します。

## <a name="syntax"></a>構文

```C
int _fileno(
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

**_fileno**は、ファイル記述子を返します。 エラーの戻り値はありません。 *ストリーム*がオープン・ファイルを指定しない場合、結果は未定義になります。 stream が**NULL**の場合 **、_fileno**は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、この関数は -1 を返し、**errno** を **EINVAL** に設定します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

> [!NOTE]
> **stdout**または**stderr**が出力ストリームに関連付けられていない場合 (たとえば、コンソール ウィンドウのない Windows アプリケーションで)、返されるファイル記述子は -2 です。 以前のバージョンでは、返されるファイル記述子は -1 でした。 この変更で、アプリケーションはこの条件をエラーと区別できるようになりました。

## <a name="remarks"></a>解説

**_fileno**ルーチンは、現在*stream*に関連付けられているファイル記述子を返します。 このルーチンは、関数とマクロの両方として実装されています。 実装の使い分けについては、「[関数とマクロの使い分け](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**_fileno**|\<stdio.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_fileno.c
// This program uses _fileno to obtain
// the file descriptor for some standard C streams.
//

#include <stdio.h>

int main( void )
{
   printf( "The file descriptor for stdin is %d\n", _fileno( stdin ) );
   printf( "The file descriptor for stdout is %d\n", _fileno( stdout ) );
   printf( "The file descriptor for stderr is %d\n", _fileno( stderr ) );
}
```

```Output
The file descriptor for stdin is 0
The file descriptor for stdout is 1
The file descriptor for stderr is 2
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_fdopen、_wfdopen](fdopen-wfdopen.md)<br/>
[_filelength、_filelengthi64](filelength-filelengthi64.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[freopen、_wfreopen](freopen-wfreopen.md)<br/>
