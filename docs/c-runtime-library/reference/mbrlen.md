---
title: mbrlen
ms.date: 4/2/2020
api_name:
- mbrlen
- _o_mbrlen
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbrlen
helpviewer_keywords:
- mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
ms.openlocfilehash: 7503de22a8310335ddd678335916d3e74dab6e70
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340987"
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

*Str*<br/>
マルチバイト文字列内の検査対象となる次のバイトへのポインター。

*count*<br/>
検査対象の最大バイト数。

*mbstate*<br/>
*str*の初期バイトの現在のシフト状態へのポインタ。

## <a name="return-value"></a>戻り値

次のいずれかの値:

|||
|-|-|
0|次の*カウント*数以下のバイト数は、ワイドヌル文字を表すマルチバイト文字を完了します。
1 を*カウント*する 、 を含む|次の*カウント*数以下のバイト数で、有効なマルチバイト文字が完成します。 返される値は、マルチバイト文字を完成するのに必要なバイト数です。
(size_t)(-2)|次の*カウント*バイトは、不完全だが有効な可能性のあるマルチバイト文字に影響し、すべての*カウント*バイトが処理されました。
(size_t)(-1)|エンコーディング エラーが発生しました。 次の*カウント*数以下のバイト数は、完全で有効なマルチバイト文字に影響しません。 この場合 **、errno**は EILSEQ に設定され *、mbstate*の変換状態は指定されません。

## <a name="remarks"></a>解説

**mbrlen**関数は *、str*が指すバイトから始まる*最大カウント*バイトを検査し、シフト シーケンスを含む次のマルチバイト文字を完了するために必要なバイト数を決定します。 これは *、mbstate*が`mbrtowc(NULL, str, count, &mbstate)`ユーザー指定の**mbstate_t**オブジェクトであるか、またはライブラリによって提供される静的内部オブジェクトである場合の呼び出しと同じです。

**mbrlen**関数は *、mbstate*パラメーター内の不完全なマルチバイト文字のシフト状態を保存して使用します。 これにより **、mbrlen**は必要に応じてマルチバイト文字の途中で再始動する機能を提供し、最大*カウント*・バイト数を検査します。 *mbstate*が null ポインターの場合 **、mbrlen**は内部の静的**mbstate_t**オブジェクトを使用してシフト状態を格納します。 内部**mbstate_t**オブジェクトはスレッド セーフではないため、常に独自の*mbstate*パラメーターを割り当てて渡すことをお勧めします。

**mbrlen**関数は[、_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)とは、その再起動可能性によって異なります。 シフト状態は、同じ関数または他の再開可能な関数を呼び出す以降の呼び出しの場合は*mbstate*に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば、wcstombs の代わりに**wcsrtombs**への後続の呼び出しを使用する場合、アプリケーションは**wcslen**ではなく**wcsrlen**を使用**する**必要があります。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|適用外|適用外|**mbrlen**|適用外|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**mbrlen**|\<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

この例では、マルチバイト文字の解釈が現在のコード ページに依存するしくみを示し、 **mbrlen**の再開機能を示します。

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
