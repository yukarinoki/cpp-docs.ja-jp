---
description: 詳細については、「fputs、fputws」を参照してください。
title: fputs、fputws
ms.date: 03/02/2021
api_name:
- fputs
- fputws
- _o_fputs
- _o_fputws
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
- fputs
- fputws
- _fputts
helpviewer_keywords:
- streams, writing strings to
- fputws function
- _fputts function
- fputs function
- fputts function
ms.openlocfilehash: 3b38f3c369a567c00f17a0f4d905de324100a3d4
ms.sourcegitcommit: c0c9cdae79f19655e809a4979227c51bb19cff63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "102236791"
---
# <a name="fputs-fputws"></a>`fputs`, `fputws`

ストリームに文字列を書き込みます。

## <a name="syntax"></a>構文

```C
int fputs(
   const char *str,
   FILE *stream
);
int fputws(
   const wchar_t *str,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*`str`*\
出力する文字列。

*`stream`*\
構造体へのポインター **`FILE`** 。

## <a name="return-value"></a>戻り値

これらの関数は、正常に終了した場合に 0 以上の値を返します。 エラーが発生した場合、とはを **`fputs`** **`fputws`** 返し **`EOF`** ます。 *`str`* または *`stream`* が null ポインターの場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数はをに設定し、を **`errno`** **`EINVAL`** 返し **`EOF`** ます。

エラーコードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

これらの各関数は、 *`str`* 出力の現在位置にをコピーし *`stream`* ます。 **`fputws`***`str`* *`stream`* *`stream`* がテキストモードとバイナリモードのどちらで開かれているかに応じて、ワイド文字の引数をマルチバイト文字列またはワイド文字列としてにコピーします。 どちらの関数も、終端の null 文字をコピーしません。

ストリームが ANSI モードで開かれている場合、2 つの関数の動作は同じになります。 **`fputs`** は、UNICODE ストリームへの出力を現在サポートしていません。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキストルーチンのマッピング

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**`_fputts`**|**`fputs`**|**`fputs`**|**`fputws`**|

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**`fputs`**|\<stdio.h>|
|**`fputws`**|\<stdio.h> または \<wchar.h>|

コンソールは、ユニバーサル Windows プラットフォーム (UWP) アプリではサポートされていません。 コンソール (、、および) に関連付けられている標準ストリームハンドルは、 **`stdin`** **`stdout`** **`stderr`** C ランタイム関数が UWP アプリで使用できるようになる前にリダイレクトする必要があります。 互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_fputs.c
// This program uses fputs to write
// a single line to the stdout stream.

#include <stdio.h>

int main( void )
{
   fputs( "Hello world from fputs.\n", stdout );
}
```

```Output
Hello world from fputs.
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)\
[`fgets`, `fgetws`](fgets-fgetws.md)\
[`gets`, `_getws`](../../c-runtime-library/gets-getws.md)\
[`puts`, `_putws`](puts-putws.md)
