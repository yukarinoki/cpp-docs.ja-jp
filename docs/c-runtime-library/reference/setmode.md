---
title: _setmode
ms.date: 4/2/2020
api_name:
- _setmode
- _o__setmode
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _setmode
helpviewer_keywords:
- Unicode [C++], console output
- files [C++], modes
- _setmode function
- file translation [C++], setting mode
- files [C++], translation
- setmode function
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
ms.openlocfilehash: abedba6f1d414191732859e3e44b54cc16acc4e9
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008425"
---
# <a name="_setmode"></a>_setmode

ファイルの変換モードを設定します。

## <a name="syntax"></a>構文

```C
int _setmode (
   int fd,
   int mode
);
```

### <a name="parameters"></a>パラメーター

*スクリプター*<br/>
ファイル記述子。

*mode*<br/>
新しい変換モード。

## <a name="return-value"></a>戻り値

成功した場合、前の変換モードを返します。

この関数に無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は-1 を返し、 **errno**を、無効なファイル記述子を示す**EBADF**、または無効な*モード*引数を示す**EINVAL**に設定します。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_Setmode**関数は、 *fd*によって指定されたファイルの変換モードを*モード*に設定します。 *モード*として **_O_TEXT**を渡すと、テキスト (変換) モードが設定されます。 キャリッジリターンラインフィード (CR-LF) の組み合わせは、入力時に1つのラインフィード文字に変換されます。 ライン フィード文字は、出力時に CR-LF の組み合わせに変換されます。 **_O_BINARY**を渡すと、変換が抑制されるバイナリ (無変換) モードが設定されます。

このドキュメントで後述する2番目の例に示すように、 **_O_U16TEXT**、 **_O_U8TEXT**、または **_O_WTEXT** を渡して Unicode モードを有効にすることもできます。

> [!CAUTION]
> Unicode モードは、ワイド印刷関数 (など) 用で `wprintf` あり、ナロー印刷関数ではサポートされていません。 Unicode モードストリームでナロー print 関数を使用すると、アサートがトリガーされます。

**_setmode** は通常、 **stdin** と **stdout**の既定の変換モードを変更するために使用されますが、任意のファイルで使用できます。 ストリームのファイル記述子に **_setmode** を適用する場合は、ストリームに対して入力または出力操作を実行する前に **_setmode** を呼び出します。

> [!CAUTION]
> ファイルストリームにデータを書き込む場合は、 **_setmode**を使用してモードを変更する前に、 [fflush](fflush.md)を使用して明示的にコードをフラッシュします。 コードをフラッシュしないと、予期しない動作が発生することがあります。 ストリームにデータを書き込んでいない場合は、コードをフラッシュする必要はありません。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**_setmode**|\<io.h>|\<fcntl.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example-use-_setmode-to-change-stdin"></a>例: _setmode を使用した stdin の変更

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

## <a name="example-use-_setmode-to-change-stdout"></a>例: _setmode を使用して stdout を変更する

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

[ファイルの処理](../../c-runtime-library/file-handling.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_set_fmode](set-fmode.md)<br/>
