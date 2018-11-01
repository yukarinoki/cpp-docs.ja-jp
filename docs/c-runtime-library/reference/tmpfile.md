---
title: tmpfile
ms.date: 11/04/2016
apiname:
- tmpfile
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
- tmpfile
helpviewer_keywords:
- temporary files
- tmpfile function
- temporary files, creating
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
ms.openlocfilehash: 98afcb7a3e04a96a1b08bc1b975634153e550839
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530326"
---
# <a name="tmpfile"></a>tmpfile

一時ファイルを作成します。 セキュリティが強化されたバージョンが提供されたため、この関数は非推奨とされました。「[tmpfile_s](tmpfile-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
FILE *tmpfile( void );
```

## <a name="return-value"></a>戻り値

成功した場合、 **tmpfile**ストリーム ポインターを返します。 それ以外を返します、 **NULL**ポインター。

## <a name="remarks"></a>Remarks

**Tmpfile**関数は、一時ファイルを作成し、そのストリームへのポインターを返します。 一時ファイルはルート ディレクトリに作成されます。 ルート ディレクトリ以外のディレクトリに一時ファイルを作成するには、[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) または [tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) を [fopen](fopen-wfopen.md) と共に使用します。

ファイルを開けない場合**tmpfile**を返します、 **NULL**ポインター。 通常、またはプログラムの終了時に、ファイルが閉じられたときに、この一時ファイルが自動的に削除 **_rmtmp**と呼ばれる場合は、現在の作業ディレクトリが変更しないと仮定します。 一時ファイルを開いた**w + b** (バイナリ読み取り/書き込み) モード。

TMP_MAX よりも多くしようとすると、エラーが発生する可能性が (STDIO を参照してください。H) 呼び出し**tmpfile**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**tmpfile**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

> [!NOTE]
> この例では、Windows Vista を管理者権限で実行する必要があります。

```C
// crt_tmpfile.c
// compile with: /W3
// This program uses tmpfile to create a
// temporary file, then deletes this file with _rmtmp.
#include <stdio.h>

int main( void )
{
   FILE *stream;
   int  i;

   // Create temporary files.
   for( i = 1; i <= 3; i++ )
   {
      if( (stream = tmpfile()) == NULL ) // C4996
      // Note: tmpfile is deprecated; consider using tmpfile_s instead
         perror( "Could not open new temporary file\n" );
      else
         printf( "Temporary file %d was created\n", i );
   }

   // Remove temporary files.
   printf( "%d temporary files deleted\n", _rmtmp() );
}
```

```Output
Temporary file 1 was created
Temporary file 2 was created
Temporary file 3 was created
3 temporary files deleted
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_rmtmp](rmtmp.md)<br/>
[_tempnam、_wtempnam、tmpnam、_wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
