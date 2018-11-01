---
title: tmpfile_s
ms.date: 11/04/2016
apiname:
- tmpfile_s
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
- tmpfile_s
helpviewer_keywords:
- temporary files
- tmpfile_s function
- temporary files, creating
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
ms.openlocfilehash: 341e1c8ed6dd20ec7e6a3d71999fb365e45e614a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488115"
---
# <a name="tmpfiles"></a>tmpfile_s

一時ファイルを作成します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [tmpfile](tmpfile.md) です。

## <a name="syntax"></a>構文

```C
errno_t tmpfile_s(
   FILE** pFilePtr
);
```

### <a name="parameters"></a>パラメーター

*pFilePtr*<br/>
ストリームに生成されたポインターのアドレスを格納するポインターのアドレスです。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|*pFilePtr*|**戻り値**|**内容***pFilePtr* |
|----------------|----------------------|---------------------------------|
|**NULL**|**EINVAL**|変更されない|

上記のパラメーターの検証エラーが発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、戻り値は**EINVAL**します。

## <a name="remarks"></a>Remarks

**Tmpfile_s**関数は、一時ファイルを作成しでそのストリームへのポインターを与えます、 *pFilePtr*引数。 一時ファイルはルート ディレクトリに作成されます。 ルート ディレクトリ以外のディレクトリに一時ファイルを作成するには、[tmpnam_s](tmpnam-s-wtmpnam-s.md) または [tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) を [fopen](fopen-wfopen.md) と共に使用します。

ファイルを開けない場合**tmpfile_s**書き込みます**NULL**を*pFilePtr*パラメーター。 通常、またはプログラムの終了時に、ファイルが閉じられたときに、この一時ファイルが自動的に削除 **_rmtmp**と呼ばれる場合は、現在の作業ディレクトリが変更しないと仮定します。 一時ファイルを開いた**w + b** (バイナリ読み取り/書き込み) モード。

しようとすると、エラーが発生する可能性が複数の**から**(STDIO を参照してください。H) 呼び出し**tmpfile_s**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**tmpfile_s**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

> [!NOTE]
> この例では、Windows で実行する管理者特権を必要があります。

```C
// crt_tmpfile_s.c
// This program uses tmpfile_s to create a
// temporary file, then deletes this file with _rmtmp.
//

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char tempstring[] = "String to be written";
   int  i;
   errno_t err;

   // Create temporary files.
   for( i = 1; i <= 3; i++ )
   {
      err = tmpfile_s(&stream);
      if( err )
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
