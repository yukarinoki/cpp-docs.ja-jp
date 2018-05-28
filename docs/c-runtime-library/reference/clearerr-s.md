---
title: clearerr_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- clearerr_s
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
- clearerr_s
dev_langs:
- C++
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr_s function
ms.assetid: b74d014d-b7a8-494a-a330-e5ffd5614772
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34feccd2d4d6de53ed9c5a446bf6c7d065dd4e62
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
---
# <a name="clearerrs"></a>clearerr_s

ストリームのエラー インジケーターをリセットします。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [clearerr](clearerr.md) です。

## <a name="syntax"></a>構文

```C
errno_t clearerr_s(
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
ポインター**ファイル**構造体

## <a name="return-value"></a>戻り値

正常終了した場合は 0 します。**EINVAL**場合*ストリーム*は**NULL**です。

## <a name="remarks"></a>コメント

**Clearerr_s**関数は、エラー インジケーターとのファイルの終端のインジケーターをリセット*ストリーム*です。 エラー インジケーターは自動的にクリアされません。このストリームでの操作が引き続きまでエラー値を返します、指定したストリームのエラー インジケーターを設定すると、 **clearerr_s**、 **clearerr**、 [fseek](fseek-fseeki64.md)、 **fsetpos**、または[巻き戻し](rewind.md)と呼びます。

場合*ストリーム*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**し、返します**EINVAL**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**clearerr_s**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_clearerr_s.c
// This program creates an error
// on the standard input stream, then clears
// it so that future reads won't fail.

#include <stdio.h>

int main( void )
{
   int c;
   errno_t err;

   // Create an error by writing to standard input.
   putc( 'c', stdin );
   if( ferror( stdin ) )
   {
      perror( "Write error" );
      err = clearerr_s( stdin );
      if (err != 0)
      {
         abort();
      }
   }

   // See if read causes an error.
   printf( "Will input cause an error? " );
   c = getc( stdin );
   if( ferror( stdin ) )
   {
      perror( "Read error" );
      err = clearerr_s( stdin );
      if (err != 0)
      {
         abort();
      }
   }
}
```

```Output

n

```

```Output

      nWrite error: Bad file descriptor
Will input cause an error? n
```

## <a name="see-also"></a>関連項目

[エラー処理](../../c-runtime-library/error-handling-crt.md)<br/>
[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[ferror](ferror.md)<br/>
[perror、_wperror](perror-wperror.md)<br/>
