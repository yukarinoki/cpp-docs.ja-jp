---
title: fwrite
ms.date: 11/04/2016
apiname:
- fwrite
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
- fwrite
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
ms.openlocfilehash: b4d6b9ce4fb66ee545f52946e28e4984d9e4f924
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506747"
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

*size*<br/>
項目サイズ (バイト単位)。

*count*<br/>
書き込む項目の最大数。

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

**fwrite**フルの数を返します、実際に書き込まれた項目なる可能性があるより小さい*カウント*エラーが発生した場合。 また、エラーが発生した場合は、ファイル位置インジケーターを決定できません。 いずれか*ストリーム*または*バッファー* null ポインター、または Unicode モードで奇数バイトが書き込まれるが指定されている場合、関数、無効なパラメーター ハンドラーを呼び出します」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**は 0 を返します。

## <a name="remarks"></a>Remarks

**Fwrite**関数は最大書き込みます*カウント*項目の*サイズ*、それぞれの長さから*バッファー*出力に*ストリーム*. 関連付けられたファイル ポインター*ストリーム*(存在する場合) が実際に書き込まれたバイト数でインクリメントされます。 場合*ストリーム*が開かれたテキスト モードでは、各ライン フィードはキャリッジ リターン - ライン フィードのペアに置き換えられます。 この置き換えは、戻り値には影響しません。

ときに*ストリーム*は Unicode 変換モードで開かれます — たとえば場合、*ストリーム*が呼び出すことによって開かれた**fopen**を含むモード パラメーターを使用して、 **ccs= UNICODE**、 **ccs = UTF 16LE**、または**ccs = utf-8**を使用して、モードが Unicode 変換モードに変更された場合または **_setmode**とモードパラメーターが含まれる **_O_WTEXT**、 **_O_U16TEXT**、または **_O_U8TEXT**—*バッファー*へのポインターとして解釈されますが、配列**wchar_t** utf-16 データを格納しています。 このモードで奇数バイトの書き込みを試みると、パラメーター検証エラーが発生します。

この関数は呼び出し元スレッドをロックするため、スレッド セーフです。 ロックしないバージョンでは、**_fwrite_nolock**を参照してください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
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
