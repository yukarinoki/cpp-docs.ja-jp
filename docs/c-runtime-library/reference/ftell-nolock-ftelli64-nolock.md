---
title: _ftell_nolock、_ftelli64_nolock
ms.date: 4/2/2020
api_name:
- _ftelli64_nolock
- _ftell_nolock
- _o__ftell_nolock
- _o__ftelli64_nolock
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
- _ftelli64_nolock
- ftelli64_nolock
- ftell_nolock
- _ftell_nolock
helpviewer_keywords:
- ftelli64_nolock function
- _ftelli64_nolock function
- _ftell_nolock function
- ftell_nolock function
- file pointers [C++], getting current position
ms.assetid: 84e68b0a-32f8-4c4a-90ad-3f2387685ede
ms.openlocfilehash: fc6534daaeb3818e28e3c48dbc6d1d9586b6429e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345593"
---
# <a name="_ftell_nolock-_ftelli64_nolock"></a>_ftell_nolock、_ftelli64_nolock

スレッドをロックせずに、ファイル ポインターの現在の位置を取得します。

## <a name="syntax"></a>構文

```C
long _ftell_nolock(
   FILE *stream
);
__int64 _ftelli64_nolock(
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
**FILE**構造体をターゲットにします。

## <a name="return-value"></a>戻り値

**フテル**と **_ftelli64**と同じです。 詳細については、「 [ftell, _ftelli64](ftell-ftelli64.md)」を参照してください。

## <a name="remarks"></a>解説

これらの関数は、それぞれ**ftell**と **_ftelli64**の非ロック バージョンです。 これらは、他のスレッドによる干渉から保護されない点を除いて **、ftell**および **_ftelli64**と同じです。 これらの関数では他のスレッドをロックアウトするオーバーヘッドが発生しないため、処理が速くなる場合があります。 これらの関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみ使用してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|オプション ヘッダー|
|--------------|---------------------|---------------------|
|**ftell_nolock**|\<stdio.h>|\<errno.h>|
|**_ftelli64_nolock**|\<stdio.h>|\<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek、_fseeki64](fseek-fseeki64.md)<br/>
[_lseek、_lseeki64](lseek-lseeki64.md)<br/>
[ftell、_ftelli64](ftell-ftelli64.md)<br/>
