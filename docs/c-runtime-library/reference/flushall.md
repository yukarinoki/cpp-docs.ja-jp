---
title: _flushall
ms.date: 4/2/2020
api_name:
- _flushall
- _o__flushall
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _flushall
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
ms.openlocfilehash: 1a53eeedd5dfa0f9c01fa5883a9db33e26e3ea17
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911625"
---
# <a name="_flushall"></a>_flushall

すべてのストリームをフラッシュし、すべてのバッファーをクリアします。

## <a name="syntax"></a>構文

```C
int _flushall( void );
```

## <a name="return-value"></a>戻り値

**_flushall**は、開いているストリーム (入力と出力) の数を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>解説

既定では、 **_flushall**関数は、開いている出力ストリームに関連付けられているすべてのバッファーの内容を適切なファイルに書き込みます。 開いている入力ストリームに関連付けられているすべてのバッファーでは、現在の内容がクリアされます。 これらのバッファーは通常はオペレーティング システムによって保持され、データをディスクに自動的に書き込むための最適なタイミングが決定されます。タイミングとしては、バッファーがいっぱいになったとき、ストリームが閉じられるとき、プログラムがストリームを閉じずに正常に終了したときがあります。

読み取りが **_flushall**の呼び出しに続いている場合、新しいデータが入力ファイルからバッファーに読み込まれます。 **_Flushall**を呼び出すと、すべてのストリームが開いたままになります。

ランタイム ライブラリのディスクへのコミットの機能を使用すると、重要なデータをオペレーティング システムのバッファーではなく、ディスクに直接書き込むことができます。 既存のプログラムを書き換えることなく、プログラムのオブジェクトファイルを Commode .obj にリンクすることで、この機能を有効にすることができます。生成された実行可能ファイルでは、を呼び出して、すべてのバッファーの内容をディスクに書き込み **_flushall**ます。 Commode .obj によって影響を受けるのは、 **_flushall**と[fflush](fflush.md)だけです。

ディスクへのコミットの機能の制御については、「[ストリーム入出力](../../c-runtime-library/stream-i-o.md)」、「[fopen](fopen-wfopen.md)」、および「[_fdopen](fdopen-wfdopen.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_flushall**|\<stdio.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

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
