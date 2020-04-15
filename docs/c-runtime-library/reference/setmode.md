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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 36d2130d4039f1f87f7f54fc26ad02cb8d519b4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353836"
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

*Fd*<br/>
ファイル記述子。

*モード*<br/>
新しい変換モード。

## <a name="return-value"></a>戻り値

成功した場合、前の変換モードを返します。

この関数に無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、この関数は -1 を返し **、errno**を無効なファイル記述子を示す**EBADF**に設定するか、無効な*モード*引数を示す**EINVAL**に設定します。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_setmode**関数は *、fd*で指定されたファイルの変換モードを*モード*に設定します。 **_O_TEXTモード**として*mode*渡すと、テキスト (つまり、翻訳) モードが設定されます。 キャリッジ リターンライン フィード (CR-LF) の組み合わせは、入力時に 1 つの改行文字に変換されます。 ライン フィード文字は、出力時に CR-LF の組み合わせに変換されます。 **_O_BINARY**渡すと、バイナリ (変換されていない) モードが設定され、これらの変換は抑制されます。

このドキュメントの後半の 2 番目**の**例で説明するように、_O_U16TEXT 、 **_O_U8TEXT**、または **_O_WTEXT**を渡して Unicode モードを有効にすることもできます。

> [!CAUTION]
> Unicode モードは、幅広い印刷機能`wprintf`( など ) 用であり、幅の狭い印刷機能ではサポートされていません。 Unicode モード ストリームで幅の狭い印刷機能を使用すると、アサートがトリガーされます。

**_setmode**は通常、 **stdin**および**stdout**のデフォルトの変換モードを変更するために使用されますが、任意のファイルで使用できます。 ストリームのファイル記述子に **_setmode**を適用する場合は、ストリームに対して入出力操作を実行する前に **、_setmode**を呼び出します。

> [!CAUTION]
> ファイル ストリームにデータを書き込む場合は、モードを変更するために **_setmode**を使用する前に[、fflush](fflush.md)を使用してコードを明示的にフラッシュします。 コードをフラッシュしないと、予期しない動作が発生することがあります。 ストリームにデータを書き込んでいない場合は、コードをフラッシュする必要はありません。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**_setmode**|\<io.h>|\<fcntl.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

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
