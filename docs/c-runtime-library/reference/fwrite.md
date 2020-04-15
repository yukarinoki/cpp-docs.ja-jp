---
title: fwrite
ms.date: 4/2/2020
api_name:
- fwrite
- _o_fwrite
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
- fwrite
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
ms.openlocfilehash: a5bd6da3c8d16189f7ff0db744901e03513acc21
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345391"
---
# <a name="fwrite"></a>fwrite

ストリームにデータを書き込みます。

## <a name="syntax"></a>構文

```C
size_t fwrite(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
書き込むデータへのポインター。

*サイズ*<br/>
項目サイズ (バイト単位)。

*count*<br/>
書き込む項目の最大数。

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

**fwrite**は実際に書き込まれた項目の数を返しますが、これはエラーが発生した場合は*カウント*より少なくなる可能性があります。 また、エラーが発生した場合は、ファイル位置インジケーターを決定できません。 *ストリーム*または*バッファー*のいずれかが null ポインターである場合、または書き込まれるバイト数が奇数の場合は、Unicode モードで指定された場合、関数は、[パラメーターの検証](../../c-runtime-library/parameter-validation.md)で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、この関数は**errno**を**EINVAL**に設定し、0 を返します。

## <a name="remarks"></a>解説

**fwrite**関数は、*バッファ*から出力*ストリーム*まで、*サイズの長*さのアイテムを*最大でカウント*します。 *ストリーム*に関連付けられたファイル ポインタ (ある場合) は、実際に書き込まれるバイト数だけインクリメントされます。 *ストリーム*がテキスト モードで開かれている場合、各行フィードは復帰と改行のペアに置き換えられます。 この置き換えは、戻り値には影響しません。

*ストリーム*が Unicode 変換モードで開かれている場合 (*stream*たとえば、ストリームが**fopen**を呼び出して開かれ **、ccs=UNICODE、ccs=UTF-16LE、** または**ccs=UTF-8**を含むモード パラメーターを使用して開かれた **_setmode**場合)、または _setmode を使用してモードが Unicode 変換モードに変更**wchar_t**され **、_O_WTEXT、_O_U16TEXT、** または **_O_U8TEXT**を含むモード パラメーターを使用して*バッファーが*utf-16 を含む配列へのポインターとして解釈wchar_t場合。 **ccs=UTF-16LE** **_O_U16TEXT** このモードで奇数バイトの書き込みを試みると、パラメーター検証エラーが発生します。

この関数は呼び出し元スレッドをロックするため、スレッド セーフです。 ロックされていないバージョンについては **、「_fwrite_nolock」** を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**fwrite**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[fread](fread.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_setmode](setmode.md)<br/>
[fread](fread.md)<br/>
[_fwrite_nolock](fwrite-nolock.md)<br/>
[_write](write.md)<br/>
