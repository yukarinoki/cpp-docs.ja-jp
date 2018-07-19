---
title: mbrlen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- mbrlen
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbrlen
dev_langs:
- C++
helpviewer_keywords:
- mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77e5cb106a971bcaf02662bfd8459267a134173a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404442"
---
# <a name="mbrlen"></a>mbrlen

現在のロケールのマルチバイト文字を完成させるのに必要なバイト数を決定します。マルチバイト文字の途中から再開することが可能です。

## <a name="syntax"></a>構文

```C
size_t mbrlen(
   const char * str,
   size_t count,
   mbstate_t * mbstate
);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
マルチバイト文字列内の検査対象となる次のバイトへのポインター。

*count*<br/>
検査対象の最大バイト数。

*呼び出すため*<br/>
最初のバイトの現在のシフト状態へのポインター *str*です。

## <a name="return-value"></a>戻り値

次のいずれかの値です。

|||
|-|-|
0|次*カウント*か、以下のバイト数をワイド null 文字を表すマルチバイト文字を完成させます。
1 ~*カウント*、包括的|次*カウント*か、以下のバイト数が有効なマルチバイト文字を完成させます。 返される値は、マルチバイト文字を完成するのに必要なバイト数です。
(size_t)(-2)|次へ*カウント*バイトは、不完全ながら有効になり得るマルチバイト文字とそのすべてに寄与*カウント*バイトが処理されています。
(size_t)(-1)|エンコーディング エラーが発生しました。 次*カウント*以下のバイト数は、完全かつ有効なマルチバイト文字に寄与しません。 この場合、 **errno**が EILSEQ に設定され、変換状態で*呼び出すため*は指定されていません。

## <a name="remarks"></a>コメント

**Mbrlen**関数が多くて検査*カウント*バイトで始まるバイトを指す*str*次を完了するために必要なバイト数を決定するにはシフト シーケンスを含むマルチバイト文字。 これは、呼び出しに相当`mbrtowc(NULL, str, count, &mbstate)`場所*呼び出すため*がいずれか、ユーザー指定**mbstate_t**オブジェクト、または、ライブラリによって提供される静的な内部オブジェクトです。

**Mbrlen**関数を格納してに不完全なマルチバイト文字のシフト状態を使用、*呼び出すため*パラメーター。 これにより、 **mbrlen**場合は、マルチバイト文字の途中から再開することができる必要があります多くて調べて*カウント*バイトです。 場合*呼び出すため*null ポインターでは、 **mbrlen**内部の静的なを使用して**mbstate_t**シフト状態を格納するオブジェクト。 内部**mbstate_t**オブジェクトはスレッド セーフではありません、常に割り当てるを独自に渡すことをお勧め*呼び出すため*パラメーター。

**Mbrlen**関数とは異なります[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)によって、再起動します。 シフト状態が格納されている*呼び出すため*以降の呼び出し、同じまたは再開可能なその他の関数にします。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば、アプリケーションを使用する必要があります**後**の代わりに**wcslen**場合、後続の呼び出しに**wcsrtombs**の代わりに使用される**wcstombs**.

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|該当なし|該当なし|**mbrlen**|該当なし|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**mbrlen**|\<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

この例では、マルチバイト文字の解釈の現在のコード ページによって異なりますされの再開機能を示しますを示しています。 **mbrlen**です。

```C
// crt_mbrlen.c
// Compile by using: cl crt_mbrlen.c
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <locale.h>
#include <wchar.h>

size_t Example(const char * pStr)
{
    size_t      charLen = 0;
    size_t      charCount = 0;
    mbstate_t   mbState = {0};

    while ((charLen = mbrlen(pStr++, 1, &mbState)) != 0 &&
            charLen != (size_t)-1)
    {
        if (charLen != (size_t)-2) // if complete mbcs char,
        {
            charCount++;
        }
    }
    return (charCount);
}

int main( void )
{
    int         cp;
    size_t      charCount = 0;
    const char  *pSample =
        "\x82\xD0\x82\xE7\x82\xAA\x82\xC8: Shift-jis hiragana.";

    cp = _getmbcp();
    charCount = Example(pSample);
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",
        cp, pSample, charCount);

    setlocale(LC_ALL, "ja-JP"); // Set Japanese locale
    _setmbcp(932); // and Japanese multibyte code page
    cp = _getmbcp();
    charCount = Example(pSample);
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",
        cp, pSample, charCount);
}
```

```Output

Code page: 0
é╨éτé¬é╚: Shift-jis hiragana.
Character count: 29

Code page: 932
????: Shift-jis hiragana.
Character count: 25

```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
