---
title: _fread_nolock_s2
ms.date: 4/2/2020
api_name:
- _fread_nolock_s
- _o__fread_nolock_s
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
- _fread_nolock_s
- stdio/_fread_nolock_s
ms.assetid: 5badb9ab-11df-4e17-8162-30bda2a4572e
ms.openlocfilehash: 3fb34a75a0281058a1d70ce41e1ce33b4b1bbb59
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346137"
---
# <a name="_fread_nolock_s"></a>_fread_nolock_s

他のスレッドをロックしないで、ストリームからデータを読み取ります。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [fread_nolock](fread-nolock.md) です。

## <a name="syntax"></a>構文

```C
size_t _fread_nolock_s(
   void *buffer,
   size_t bufferSize,
   size_t elementSize,
   size_t elementCount,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
データの格納場所。

*Buffersize*<br/>
ターゲット バッファーのサイズ (バイト単位)。

*要素サイズ*<br/>
読み取る項目のサイズ (バイト単位)。

*要素数*<br/>
読み取る項目の最大数。

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

「[fread_s](fread-s.md)」を参照してください。

## <a name="remarks"></a>解説

この関数はロックされていないバージョンの**fread_s**です。 他のスレッドによる干渉から保護されていない点を除いて **、fread_s**と同じです。 他のスレッドをロックするオーバーヘッドが発生しないため、処理が速くなる場合があります。 この関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみご使用ください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**_fread_nolock_s**|C: \<stdio.h>、C++: \<cstdio>、または \<stdio.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
