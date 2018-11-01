---
title: _getchar_nolock、_getwchar_nolock
ms.date: 11/04/2016
apiname:
- _getchar_nolock
- _getwchar_nolock
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
apitype: DLLExport
f1_keywords:
- getwchar_nolock
- _getwchar_nolock
- _getchar_nolock
- getchar_nolock
helpviewer_keywords:
- _getwchar_nolock function
- getwchar_nolock function
- characters, reading
- _getchar_nolock function
- getchar_nolock function
- standard input, reading from
ms.assetid: dc49ba60-0647-4ae9-aa9a-a0618b1666de
ms.openlocfilehash: feeda65d06dbcfecb6ea5adc60934abf3d0df415
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600139"
---
# <a name="getcharnolock-getwcharnolock"></a>_getchar_nolock、_getwchar_nolock

標準入力から文字を読み取ります。

## <a name="syntax"></a>構文

```C
int _getchar_nolock( void );
wint_t _getwchar_nolock( void );
```

## <a name="return-value"></a>戻り値

「[getchar、getwchar](getchar-getwchar.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**_getchar_nolock**と **_getwchar_nolock**と同じ**getchar**と**getwchar**する点を除いて、他の干渉から保護されません。スレッド。 他のスレッドをロックアウトするオーバーヘッドが発生しないため、処理が速くなる場合があります。 これらの関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみ使用してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_gettchar_nolock**|**_getchar_nolock**|**_getchar_nolock**|**_getwchar_nolock**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_getchar_nolock**|\<stdio.h>|
|**_getwchar_nolock**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールがサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル**stdin**、 **stdout**、および**stderr**、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_getchar_nolock.c
// Use _getchar_nolock to read a line from stdin.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;

    for (i = 0; (i < 80) && ((ch = _getchar_nolock()) != EOF)
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
