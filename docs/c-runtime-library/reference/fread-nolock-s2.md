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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fread_nolock_s
- stdio/_fread_nolock_s
ms.assetid: 5badb9ab-11df-4e17-8162-30bda2a4572e
ms.openlocfilehash: 702264f3728b0d9eca3f2fb51ba2ea0467b592df
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912730"
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

*格納*<br/>
データの格納場所。

*bufferSize*<br/>
ターゲット バッファーのサイズ (バイト単位)。

*elementSize*<br/>
読み取る項目のサイズ (バイト単位)。

*elementCount*<br/>
読み取る項目の最大数。

*一連*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

「[fread_s](fread-s.md)」を参照してください。

## <a name="remarks"></a>解説

この関数は、 **fread_s**のロックされていないバージョンです。 これは、他のスレッドによる干渉から保護されない点を除いて、 **fread_s**と同じです。 他のスレッドをロックするオーバーヘッドが発生しないため、処理が速くなる場合があります。 この関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみご使用ください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_fread_nolock_s**|C: \<stdio.h>、C++: \<cstdio>、または \<stdio.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
