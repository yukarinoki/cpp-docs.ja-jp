---
title: setbuf
ms.date: 04/08/2019
apiname:
- setbuf
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
- setbuf
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
ms.openlocfilehash: 89f8a4d8eb853c774f4f7299ceaa9b9eb6177b42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356394"
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

*stream*<br/>
**FILE** 構造体へのポインター。

*バッファー*<br/>
ユーザー割り当てのバッファー。

## <a name="remarks"></a>Remarks

**Setbuf**関数のバッファリングを制御*ストリーム*します。 *ストリーム*引数は、読み取りまたは書き込みされていないを開いているファイルを指す必要があります。 場合、*バッファー*引数が**NULL**ストリームがバッファー内ではありません。 場合は、バッファーが長さの文字配列 をポイントする必要があります、 **BUFSIZ**ここで、 **BUFSIZ** STDIO で定義されているバッファー サイズは、します。H. 所定のストリームに対してシステムによって割り当てられた既定のバッファーではなく、ユーザーが指定したバッファーが I/O バッファー処理に使用されます。 **Stderr**ストリームは既定では、バッファーなし、使用することが**setbuf**にバッファーを割り当てる**stderr**します。

**setbuf**置き換わりました[setvbuf](setvbuf.md)、これは、新しいコード用の優先ルーチンです。 異なり**setvbuf**、 **setbuf**エラーの報告方法がありません。 **setvbuf**バッファリング モードとバッファー サイズの両方を制御することもできます。 **setbuf**既存のコードとの互換性のために存在します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
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
