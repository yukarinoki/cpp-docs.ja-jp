---
title: fwrite | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1320bcc61830833f2b1a4a225dff30652df2d3a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32400581"
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

**fwrite**フルの数を返しますアイテムが実際に書き込まれた可能性もありますより小さい*カウント*エラーが発生した場合。 また、エラーが発生した場合は、ファイル位置インジケーターを決定できません。 いずれか*ストリーム*または*バッファー* null ポインターでは、または書き込まれるバイトの数が奇数が Unicode モードで指定されている場合、関数によって呼び出されます、無効なパラメーター ハンドラーを記載[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**は 0 を返します。

## <a name="remarks"></a>コメント

**Fwrite**関数は最大書き込みます*カウント*、項目の*サイズ*、それぞれの長さから*バッファー*出力に*ストリーム*. 関連付けられたファイル ポインター*ストリーム*(存在する場合) が、実際に書き込まれたバイト数だけインクリメントされます。 場合*ストリーム*が開かれているテキスト モードでは、各ライン フィードはキャリッジ リターン、ライン フィードのペアに置き換えられます。 この置き換えは、戻り値には影響しません。

ときに*ストリーム*が Unicode 変換モードで開かれる — たとえば場合、*ストリーム*を呼び出すことによって開く**fopen**を含むモード パラメーターを使用して**ccs= UNICODE**、 **ccs = UTF 16LE**、または**ccs utf-8 を =** を使用してモードが Unicode 変換モードに変更された場合または **_setmode**とモードパラメーターを含む **_O_WTEXT**、 **_O_U16TEXT**、または **_O_U8TEXT**—*バッファー*へのポインターとして解釈されますが、配列**wchar_t** utf-16 データが含まれます。 このモードで奇数バイトの書き込みを試みると、パラメーター検証エラーが発生します。

この関数は呼び出し元スレッドをロックするため、スレッド セーフです。 ロックしないバージョンでは、次を参照してください。 **_fwrite_nolock**です。

## <a name="requirements"></a>要件

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
