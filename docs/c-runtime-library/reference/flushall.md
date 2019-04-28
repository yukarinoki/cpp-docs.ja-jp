---
title: _flushall
ms.date: 11/04/2016
apiname:
- _flushall
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
- _flushall
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
ms.openlocfilehash: de8caf30568816f41441f5d9487293c346d2bff1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333535"
---
# <a name="flushall"></a>_flushall

すべてのストリームをフラッシュし、すべてのバッファーをクリアします。

## <a name="syntax"></a>構文

```C
int _flushall( void );
```

## <a name="return-value"></a>戻り値

**_flushall** (入力と出力)、開いているストリームの数を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>Remarks

既定で、 **_flushall**適切なファイルを開いている出力ストリームに関連付けられているすべてのバッファーの内容を関数に書き込みます。 開いている入力ストリームに関連付けられているすべてのバッファーでは、現在の内容がクリアされます。 これらのバッファーは通常はオペレーティング システムによって保持され、データをディスクに自動的に書き込むための最適なタイミングが決定されます。タイミングとしては、バッファーがいっぱいになったとき、ストリームが閉じられるとき、プログラムがストリームを閉じずに正常に終了したときがあります。

読み取りの呼び出しに従う場合 **_flushall**バッファーに入力ファイルから新しいデータを読み取る。 呼び出しの後のすべてのストリームが開いたまま **_flushall**します。

ランタイム ライブラリのディスクへのコミットの機能を使用すると、重要なデータをオペレーティング システムのバッファーではなく、ディスクに直接書き込むことができます。 プログラムのオブジェクト ファイルを Commode.obj にリンクすると、既存のプログラムを書き直さずに、この機能を有効にできます。呼び出し、結果として得られる実行可能ファイルで **_flushall**をディスクにすべてのバッファーの内容を記述します。 のみ **_flushall**と[fflush](fflush.md) Commode.obj の影響を受けます。

ディスクへのコミットの機能の制御については、「[ストリーム入出力](../../c-runtime-library/stream-i-o.md)」、「[fopen](fopen-wfopen.md)」、および「[_fdopen](fdopen-wfdopen.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_flushall**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_flushall.c
// This program uses _flushall
// to flush all open buffers.

#include <stdio.h>

int main( void )
{
   int numflushed;

   numflushed = _flushall();
   printf( "There were %d streams flushed\n", numflushed );
}
```

```Output
There were 3 streams flushed
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_commit](commit.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[setvbuf](setvbuf.md)<br/>
