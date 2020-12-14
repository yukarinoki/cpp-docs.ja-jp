---
description: '詳細については、次を参照してください: _getw'
title: _getw
ms.date: 4/2/2020
api_name:
- _getw
- _o__getw
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
- _getw
helpviewer_keywords:
- _getw function
- integers, getting from streams
- getw function
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
ms.openlocfilehash: 2f951305351b4693b9787b6eac926c719afd3f3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296538"
---
# <a name="_getw"></a>_getw

ストリームから整数を取得します。

## <a name="syntax"></a>構文

```C
int _getw(
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*一連*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

**_getw** は、読み取られた整数値を返します。 **EOF** の戻り値は、エラーまたはファイルの末尾を示します。 ただし、 **EOF** 値も正しい整数値であるため、 **feof** または **ferror** を使用して、ファイルの終わりまたはエラーの状態を確認します。 *Stream* が **NULL** の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、 **errno** は **EINVAL** に設定され、関数は **EOF** を返します。

## <a name="remarks"></a>解説

**_Getw** 関数は、ストリームに関連付けられているファイルから型の次のバイナリ値を読み取り **`int`** 、関連付けられているファイルポインターがある場合はそれをインクリメントして、次の未読文字を指すようにします。 **_getw** は、ストリーム内の項目の特別な配置を想定していません。 **_Getw** では、型のサイズ **`int`** と型内のバイトの順序が **`int`** システム間で異なるため、移植に関する問題が発生する可能性があります。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_getw**|\<stdio.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_getw.c
// This program uses _getw to read a word
// from a stream, then performs an error check.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   int i;

   if( fopen_s( &stream, "crt_getw.txt", "rb" ) )
      printf( "Couldn't open file\n" );
   else
   {
      // Read a word from the stream:
      i = _getw( stream );

      // If there is an error...
      if( ferror( stream ) )
      {
         printf( "_getw failed\n" );
         clearerr_s( stream );
      }
      else
         printf( "First data word in file: 0x%.4x\n", i );
      fclose( stream );
   }
}
```

### <a name="input-crt_getwtxt"></a>入力: crt_getw.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>出力

```Output
First data word in file: 0x656e694c
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_putw](putw.md)<br/>
