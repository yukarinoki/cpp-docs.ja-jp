---
title: clearerr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- clearerr
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
- clearerr
dev_langs:
- C++
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr function
ms.assetid: a9711cd4-3335-43d4-a018-87bbac5b3bac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c78355277fbb987d82bed46fb0b5f4ffd848b6a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395303"
---
# <a name="clearerr"></a>clearerr

ストリームのエラー インジケーターをリセットします。 この関数のセキュリティが強化されたバージョンについては、「[clearerr_s](clearerr-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
void clearerr(
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*へのポインター**ファイル**構造体。

## <a name="remarks"></a>コメント

**Clearerr**関数は、エラー インジケーターとのファイルの終端のインジケーターをリセット*ストリーム*です。 エラー インジケーターは自動的にクリアされません。このストリームでの操作が引き続きまでエラー値を返します、指定したストリームのエラー インジケーターを設定すると、 **clearerr**、 [fseek](fseek-fseeki64.md)、 **fsetpos**、または[巻き戻し](rewind.md)と呼びます。

場合*ストリーム*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**を返します。 詳細については**errno**エラー コードを参照してください、 [errno 定数](../../c-runtime-library/errno-constants.md)です。

この関数のセキュリティが強化されたバージョンについては、「[clearerr_s](clearerr-s.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**clearerr**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_clearerr.c
// This program creates an error
// on the standard input stream, then clears
// it so that future reads won't fail.

#include <stdio.h>

int main( void )
{
   int c;
   // Create an error by writing to standard input.
   putc( 'c', stdin );
   if( ferror( stdin ) )
   {
      perror( "Write error" );
      clearerr( stdin );
   }

   // See if read causes an error.
   printf( "Will input cause an error? " );
   c = getc( stdin );
   if( ferror( stdin ) )
   {
      perror( "Read error" );
      clearerr( stdin );
   }
   else
      printf( "No read error\n" );
}
```

```Output

n

```

```Output

      nWrite error: No error
Will input cause an error? n
No read error
```

## <a name="see-also"></a>関連項目

[エラー処理](../../c-runtime-library/error-handling-crt.md)<br/>
[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[ferror](ferror.md)<br/>
[perror、_wperror](perror-wperror.md)<br/>
