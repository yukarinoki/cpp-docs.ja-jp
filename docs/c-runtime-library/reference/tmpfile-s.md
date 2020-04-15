---
title: tmpfile_s
ms.date: 4/2/2020
api_name:
- tmpfile_s
- _o_tmpfile_s
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
- tmpfile_s
helpviewer_keywords:
- temporary files
- tmpfile_s function
- temporary files, creating
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
ms.openlocfilehash: 8f9dd58abdf1d3225341e40661c14ae3a5013257
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362462"
---
# <a name="tmpfile_s"></a>tmpfile_s

一時ファイルを作成します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [tmpfile](tmpfile.md) です。

## <a name="syntax"></a>構文

```C
errno_t tmpfile_s(
   FILE** pFilePtr
);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ストリームに生成されたポインターのアドレスを格納するポインターのアドレスです。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|*をクリックします。*|**戻り値**|**の内容***pFilePtr*  |
|----------------|----------------------|---------------------------------|
|**NULL**|**Einval**|変更されない|

上記のパラメーターの検証エラーが発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合 **、errno**は**EINVAL**に設定され、戻り値は**EINVAL**に設定されます。

## <a name="remarks"></a>解説

**tmpfile_s**関数は、一時ファイルを作成し、そのストリームへのポインターを*pFilePtr*引数に入れます。 一時ファイルはルート ディレクトリに作成されます。 ルート ディレクトリ以外のディレクトリに一時ファイルを作成するには、[tmpnam_s](tmpnam-s-wtmpnam-s.md) または [tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) を [fopen](fopen-wfopen.md) と共に使用します。

ファイルを開くことができない場合 **、tmpfile_s***は、pFilePtr*パラメーターに**NULL**を書き込みます。 この一時ファイルは、ファイルが閉じられたときに、プログラムが正常に終了したとき、または **_rmtmp**が呼び出されたときに、現在の作業ディレクトリが変更されないと、自動的に削除されます。 一時ファイルは**w+b** (バイナリ読み取り/書き込み) モードで開かれます。

**TMP_MAX_S**を超えようとすると、障害が発生する可能性があります (STDIO を参照してください。H) **tmpfile_s**との呼び出し.

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**tmpfile_s**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

> [!NOTE]
> この例では、Windows で実行するために管理者権限が必要になる場合があります。

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
