---
title: _set_fmode
ms.date: 4/2/2020
api_name:
- _set_fmode
- _o__set_fmode
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
- _set_fmode
- set_fmode
helpviewer_keywords:
- file translation [C++], default mode
- _set_fmode function
- file translation [C++], setting mode
- set_fmode function
ms.assetid: f80eb9c7-733b-4652-a9bc-6b3790a35f12
ms.openlocfilehash: ba8a4b3867eb0a18d4a14cb2f5480bc5800303c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337707"
---
# <a name="_set_fmode"></a>_set_fmode

ファイル入出力操作の既定のファイル変換モードを設定します。

## <a name="syntax"></a>構文

```C
errno_t _set_fmode(
   int mode
);
```

### <a name="parameters"></a>パラメーター

*モード*<br/>
必要なファイル変換モード: **_O_TEXT**または **_O_BINARY**。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を、失敗した場合はエラー コードを返します。 *mode*が **_O_TEXT**または **_O_BINARY**または **_O_WTEXT**されていない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、この関数は**errno**を**EINVAL**に設定し **、EINVAL**を返します。

## <a name="remarks"></a>解説

この関数は、[_fmode](../../c-runtime-library/fmode.md) グローバル変数を設定します。 この変数は、ファイル入出力操作 **_open**および **_pipe**のデフォルトのファイル変換モードを指定します。

**_O_TEXT**と **_O_BINARY**は Fcntl.h で定義されます。 **EINVAL**は Errno.h で定義されています。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_set_fmode**|\<stdlib.h>|\<fcntl.h>、\<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_set_fmode.c
#include <stdlib.h>
#include <stdio.h>
#include <fcntl.h>     /* for _O_TEXT and _O_BINARY */
#include <errno.h>     /* for EINVAL */
#include <sys\stat.h>  /* for _S_IWRITE */
#include <share.h>     /* for _SH_DENYNO */

int main()
{
   int mode, fd, ret;
   errno_t err;
   int buf[12] = { 65, 66, 67, 68, 69, 70, 71, 72, 73, 74,
                   75, 76 };
   char * filename = "fmode.out";

   err = _get_fmode(&mode);
   if (err == EINVAL)
   {
      printf( "Invalid parameter: mode\n");
      return 1;
   }
   else
      printf( "Default Mode is %s\n", mode == _O_TEXT ? "text" :
              "binary");

   err = _set_fmode(_O_BINARY);
   if (err == EINVAL)
   {
      printf( "Invalid mode.\n");
      return 1;
   }

   if ( _sopen_s(&fd, filename, _O_RDWR | _O_CREAT, _SH_DENYNO, _S_IWRITE | _S_IREAD) != 0 )
   {
      printf( "Error opening the file %s\n", filename);
      return 1;
   }

   if (ret = _write(fd, buf, 12*sizeof(int)) < 12*sizeof(int))
   {
      printf( "Problem writing to the file %s.\n", filename);
      printf( "Number of bytes written: %d\n", ret);
   }

   if (_close(fd) != 0)
   {
      printf("Error closing the file %s. Error code %d.\n",
             filename, errno);
   }

   system("type fmode.out");
}
```

```Output
Default Mode is binary
A   B   C   D   E   F   G   H   I   J   K   L
```

## <a name="see-also"></a>関連項目

[_fmode](../../c-runtime-library/fmode.md)<br/>
[_get_fmode](get-fmode.md)<br/>
[_setmode](setmode.md)<br/>
[テキストおよびバイナリ モード ファイル I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
