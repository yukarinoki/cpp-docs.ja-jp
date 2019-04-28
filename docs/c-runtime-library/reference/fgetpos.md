---
title: fgetpos
ms.date: 11/04/2016
apiname:
- fgetpos
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
- fgetpos
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
ms.openlocfilehash: e213c9830ffe6edf04b12a80828f14cc48f77524
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333931"
---
# <a name="fgetpos"></a>fgetpos

ストリームのファイル位置インジケーターを取得します。

## <a name="syntax"></a>構文

```C
int fgetpos(
   FILE *stream,
   fpos_t *pos
);
```

### <a name="parameters"></a>パラメーター

*stream*<br/>
対象のストリーム。

*pos*<br/>
位置インジケーターのストレージ。

## <a name="return-value"></a>戻り値

成功した場合、 **fgetpos** 0 を返します。 失敗した場合、0 以外の値を返す設定と**errno**次のいずれかのマニフェスト定数 (STDIO で定義されています。H):**EBADF**、つまり、指定したストリームが有効なファイル ポインターでないまたはアクセスできない、または**EINVAL**、つまり、*ストリーム*値または値の*pos*がいる場合など、有効ないずれかが null ポインターでないです。 場合*ストリーム*または*pos*は、 **NULL**ポインター、関数は無効なパラメーター ハンドラーを呼び出します」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md).

## <a name="remarks"></a>Remarks

**Fgetpos**関数の現在の値を取得、*ストリーム*引数のファイル位置インジケーターとストアによって、オブジェクトで示される*pos*します。**Fsetpos**関数は、保存されている情報を後で使用できる*pos*をリセットする、*ストリーム*時にその位置への引数のポインター **fgetpos**が呼び出されました。 *Pos*値は、内部形式で格納し、でのみで使用は想定されて**fgetpos**と**fsetpos**します。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**fgetpos**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fgetpos.c
// This program uses fgetpos and fsetpos to
// return to a location in a file.

#include <stdio.h>

int main( void )
{
   FILE   *stream;
   fpos_t pos;
   char   buffer[20];

   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {
      perror( "Trouble opening file" );
      return -1;
   }

   // Read some data and then save the position.
   fread( buffer, sizeof( char ), 8, stream );
   if( fgetpos( stream, &pos ) != 0 ) {
      perror( "fgetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fgetpos: %.13s\n", buffer );

   // Restore to old position and read data
   if( fsetpos( stream, &pos ) != 0 ) {
      perror( "fsetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fsetpos: %.13s\n", buffer );
   fclose( stream );
}
```

## <a name="input-crtfgetpostxt"></a>入力: crt_fgetpos.txt

```Input
fgetpos gets a stream's file-position indicator.
```

### <a name="output-crtfgetpostxt"></a>出力: crt_fgetpos.txt

```Output
after fgetpos: gets a stream
after fsetpos: gets a stream
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fsetpos](fsetpos.md)<br/>
