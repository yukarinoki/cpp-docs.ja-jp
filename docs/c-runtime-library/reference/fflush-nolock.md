---
description: '詳細については、次を参照してください: _fflush_nolock'
title: _fflush_nolock
ms.date: 4/2/2020
api_name:
- _fflush_nolock
- _o__fflush_nolock
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
- fflush_nolock
- _fflush_nolock
helpviewer_keywords:
- fflush_nolock function
- _fflush_nolock function
- streams, flushing
- flushing
ms.assetid: 5e33c4a1-b10c-4001-ad01-210757919291
ms.openlocfilehash: 77b2db1c26a5121b74a8c3b92c50ac41af153802
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289284"
---
# <a name="_fflush_nolock"></a>_fflush_nolock

スレッドをロックせずにストリームをフラッシュします。

## <a name="syntax"></a>構文

```C
int _fflush_nolock(
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*一連*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

「[fflush](fflush.md)」を参照してください。

## <a name="remarks"></a>解説

この関数は、 **fflush** の非ロックバージョンです。 他のスレッドによる干渉から保護されない点を除いて、 **fflush** と同じです。 他のスレッドをロックするオーバーヘッドが発生しないため、処理が速くなる場合があります。 この関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみご使用ください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|機能|必須ヘッダー|
|--------------|---------------------|
|**_fflush_nolock**|\<stdio.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[_flushall](flushall.md)<br/>
[setvbuf](setvbuf.md)<br/>
