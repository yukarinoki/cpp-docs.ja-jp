---
title: setbuf
ms.date: 4/2/2020
api_name:
- setbuf
- _o_setbuf
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
- setbuf
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
ms.openlocfilehash: f96cffb8770cda78ebff8d873b441ddc288bc41f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332078"
---
# <a name="setbuf"></a>setbuf

ストリーム バッファリングを制御します。 この関数は非推奨とされました。代わりに [setvbuf](setvbuf.md) をご使用ください。

## <a name="syntax"></a>構文

```C
void setbuf(
   FILE *stream,
   char *buffer
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
**FILE** 構造体へのポインター。

*バッファー*<br/>
ユーザー割り当てのバッファー。

## <a name="remarks"></a>解説

**setbuf**関数は *、ストリーム*のバッファリングを制御します。 *ストリーム*引数は、読み取りまたは書き込みが行われていない開いているファイルを参照する必要があります。 *buffer*引数が**NULL**の場合、ストリームはバッファリングされません。 そうでなければ、バッファーは長さの**BUFSIZ**の文字配列を指している必要**BUFSIZ**があります。H。 所定のストリームに対してシステムによって割り当てられた既定のバッファーではなく、ユーザーが指定したバッファーが I/O バッファー処理に使用されます。 **stderr**ストリームはデフォルトではバッファリングされませんが **、setbuf**を使用して、バッファを**stderr**に割り当てることができます。

**setbuf**は[setvbuf](setvbuf.md)に置き換えられました。 **setvbuf**とは異なり **、setbuf**にはエラーを報告する方法がありません。 **setvbuf**では、バッファリング モードとバッファ サイズの両方を制御することもできます。 既存のコードとの互換性のために**setbuf**が存在します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**setbuf**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_setbuf.c
// compile with: /W3
// This program first opens files named DATA1 and
// DATA2. Then it uses setbuf to give DATA1 a user-assigned
// buffer and to change DATA2 so that it has no buffer.

#include <stdio.h>

int main( void )
{
   char buf[BUFSIZ];
   FILE *stream1, *stream2;

   fopen_s( &stream1, "data1", "a" );
   fopen_s( &stream2, "data2", "w" );

   if( (stream1 != NULL) && (stream2 != NULL) )
   {
      // "stream1" uses user-assigned buffer:
      setbuf( stream1, buf ); // C4996
      // Note: setbuf is deprecated; consider using setvbuf instead
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );

      // "stream2" is unbuffered
      setbuf( stream2, NULL ); // C4996
      printf( "stream2 buffering disabled\n" );
      _fcloseall();
   }
}
```

```Output
stream1 set to user-defined buffer at: 0012FCDC
stream2 buffering disabled
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[setvbuf](setvbuf.md)<br/>
