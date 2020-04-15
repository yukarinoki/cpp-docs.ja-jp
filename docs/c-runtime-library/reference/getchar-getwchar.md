---
title: getchar、getwchar
ms.date: 4/2/2020
api_name:
- getchar
- getwchar
- _o_getchar
- _o_getwchar
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
- getwchar
- GetChar
helpviewer_keywords:
- gettchar function
- characters, reading
- getwchar function
- _gettchar function
- standard input, reading from
ms.assetid: 19fda588-3e33-415c-bb60-dd73c028086a
ms.openlocfilehash: 4311b5b896a5a406ebe14f09e7bb525cb47951b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344614"
---
# <a name="getchar-getwchar"></a>getchar、getwchar

標準入力から文字を読み取ります。

## <a name="syntax"></a>構文

```C
int getchar();
wint_t getwchar();
```

## <a name="return-value"></a>戻り値

読み取られた文字を返します。 読み取りエラーまたはファイルの終わりの条件を示すには **、getchar は** **EOF**を返し **、getwchar は** **WEOF**を返します。 **getchar**の場合は **、ferror**または**feof**を使用して、エラーまたはファイルの終わりをチェックします。

## <a name="remarks"></a>解説

各ルーチンは **、stdin**から 1 文字を読み取り、関連するファイル ポインタをインクリメントして次の文字を指します。 **getchar**は[_fgetchar](fgetc-fgetwc.md)と同じですが、関数およびマクロとして実装されます。

これらの関数は呼び出し元スレッドをロックするため、スレッド セーフです。 ロックしないバージョンについては、「[_getchar_nolock、_getwchar_nolock](getchar-nolock-getwchar-nolock.md)」をご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettchar**|**Getchar**|**Getchar**|**getwchar**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**Getchar**|\<stdio.h>|
|**getwchar**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールはサポートされていません。 コンソール **、stdin 、stdout**、および**stdout****stderr**に関連付けられている標準ストリーム ハンドルは、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_getchar.c
// Use getchar to read a line from stdin.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;

    for (i = 0; (i < 80) && ((ch = getchar()) != EOF)
                         && (ch != '\n'); i++)
    {
        buffer[i] = (char) ch;
    }

    // Terminate string with a null character
    buffer[i] = '\0';
    printf( "Input was: %s\n", buffer);
}
```

```Output

This textInput was: This text
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[getc、getwc](getc-getwc.md)<br/>
[fgetc、fgetwc](fgetc-fgetwc.md)<br/>
[_getch、_getwch](getch-getwch.md)<br/>
[putc、putwc](putc-putwc.md)<br/>
[ungetc、ungetwc](ungetc-ungetwc.md)<br/>
