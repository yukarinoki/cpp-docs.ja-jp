---
title: _fwrite_nolock
ms.date: 11/04/2016
apiname:
- _fwrite_nolock
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
- _fwrite_nolock
- fwrite_nolock
helpviewer_keywords:
- fwrite_nolock function
- streams, writing data to
- _fwrite_nolock function
ms.assetid: 2b4ec6ce-742e-4615-8407-44a0a18ec1d7
ms.openlocfilehash: 1c899e34e19547b30a42135f3f818f220f1bc5b7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626056"
---
# <a name="fwritenolock"></a>_fwrite_nolock

スレッドをロックせずにストリームにデータを書き込みます。

## <a name="syntax"></a>構文

```C
size_t _fwrite_nolock(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
書き込むデータへのポインター。

*size*<br/>
項目サイズ (バイト単位)。

*count*<br/>
書き込む項目の最大数。

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

[fwrite](fwrite.md) と同じです。

## <a name="remarks"></a>Remarks

この関数は、ロックしないバージョンの**fwrite**します。 これは**fwrite**いない他のスレッドによる干渉から保護には、する点を除いて。 他のスレッドをロックするオーバーヘッドが発生しないため、処理が速くなる場合があります。 この関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみご使用ください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_fwrite_nolock**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[fread](fread.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fread](fread.md)<br/>
[_write](write.md)<br/>
