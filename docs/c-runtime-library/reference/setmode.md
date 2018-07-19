---
title: _setmode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _setmode
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
- _setmode
dev_langs:
- C++
helpviewer_keywords:
- Unicode [C++], console output
- files [C++], modes
- _setmode function
- file translation [C++], setting mode
- files [C++], translation
- setmode function
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59aed27ec4803cd1709635da44ef37d748342e29
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407497"
---
# <a name="setmode"></a>_setmode

ファイルの変換モードを設定します。

## <a name="syntax"></a>構文

```C
int _setmode (
   int fd,
   int mode
);
```

### <a name="parameters"></a>パラメーター

*fd*<br/>
ファイル記述子。

*モード*<br/>
新しい変換モード。

## <a name="return-value"></a>戻り値

成功した場合、前の変換モードを返します。

この関数に無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように無効なパラメーター ハンドラーが呼び出されます。 実行の続行には、この関数は-1 を返しセットが許可された場合**errno**いずれかに**EBADF**、無効なファイル記述子を示すまたは**EINVAL**、無効なことを示します*モード*引数。

リターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

**_Setmode**関数に設定*モード*により与えられたファイルの変換モード*fd*です。 渡す **_O_TEXT**として*モード*設定テキスト (変換) モード。 キャリッジ リターンとライン フィード (CR-LF) の組み合わせは、1 つのライン フィード文字の入力に変換されます。 ライン フィード文字は、出力時に CR-LF の組み合わせに変換されます。 渡す **_O_BINARY**バイナリ (無変換) モードを設定、これらの翻訳が抑制されます。

渡すことも **_O_U16TEXT**、 **_O_U8TEXT**、または **_O_WTEXT**このドキュメントの後半では、2 番目の例に示すように、Unicode モードを有効にします。 **_setmode**の既定の変換モードを変更することは通常**stdin**と**stdout**、任意のファイルで行うこともできますが、します。 適用する場合 **_setmode**ストリームのファイル記述子を呼び出す **_setmode**ストリームでその入力または出力の操作を実行する前にします。

> [!CAUTION]
> コードを記述するデータ、ファイル ストリームを明示的にフラッシュを使用して場合[fflush](fflush.md)を使用する前に **_setmode**モードを変更します。 コードをフラッシュしないと、予期しない動作が発生することがあります。 ストリームにデータを書き込んでいない場合は、コードをフラッシュする必要はありません。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**_setmode**|\<io.h>|\<fcntl.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_setmode.c
// This program uses _setmode to change
// stdin from text mode to binary mode.

#include <stdio.h>
#include <fcntl.h>
#include <io.h>

int main( void )
{
   int result;

   // Set "stdin" to have binary mode:
   result = _setmode( _fileno( stdin ), _O_BINARY );
   if( result == -1 )
      perror( "Cannot set mode" );
   else
      printf( "'stdin' successfully changed to binary mode\n" );
}
```

```Output
'stdin' successfully changed to binary mode
```

## <a name="example"></a>例

```C
// crt_setmodeunicode.c
// This program uses _setmode to change
// stdout to Unicode. Cyrillic and Ideographic
// characters will appear on the console (if
// your console font supports those character sets).

#include <fcntl.h>
#include <io.h>
#include <stdio.h>

int main(void) {
    _setmode(_fileno(stdout), _O_U16TEXT);
    wprintf(L"\x043a\x043e\x0448\x043a\x0430 \x65e5\x672c\x56fd\n");
    return 0;
}
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_set_fmode](set-fmode.md)<br/>
