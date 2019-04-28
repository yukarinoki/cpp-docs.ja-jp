---
title: mbrtowc
ms.date: 11/04/2016
apiname:
- mbrtowc
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbrtowc
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
ms.openlocfilehash: bd719e7b336333f6e06a1db9b1e34784575a1602
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331533"
---
# <a name="mbrtowc"></a>mbrtowc

現在のロケールのマルチバイト文字を、それに対応するワイド文字に変換します。マルチバイト文字の途中から再開することが可能です。

## <a name="syntax"></a>構文

```C
size_t mbrtowc(
   wchar_t *wchar,
   const char *mbchar,
   size_t count,
   mbstate_t *mbstate
);
```

### <a name="parameters"></a>パラメーター

*wchar*<br/>
変換されたワイド文字の文字列を受け取るワイド文字のアドレス (型**wchar_t**)。 ワイド文字を返す必要がない場合、この値は null ポインターを指定できます。

*mbchar*<br/>
バイト シーケンスのアドレス (マルチバイト文字)。

*count*<br/>
チェックするバイト数。

*mbstate*<br/>
変換状態のオブジェクトへのポインター。 この値が null ポインターの場合、関数は静的な内部変換状態オブジェクトを使用します。 内部**mbstate_t**オブジェクトはスレッド セーフではありませんを常に渡す独自ことをお勧めします。*呼び出すため*引数。

## <a name="return-value"></a>戻り値

次のいずれかの値です。

0、[次へ]*カウント*以下のバイトに格納されている null ワイド文字を表すマルチバイト文字を完成するまたは*wchar*場合は、 *wchar*が null ポインターでないです。

1 に*数*、包括的次*数*または以下のバイトが有効なマルチバイト文字を完成します。 返される値は、マルチバイト文字を完成するのに必要なバイト数です。 相当するワイド文字が格納されている*wchar*場合は、 *wchar* null ポインターではありません。

(size_t)(-1)エンコーディング エラーが発生しました。 次*カウント*または以下のバイトは、完全かつ有効なマルチバイト文字には影響しません。 この場合、 **errno** EILSEQ と変換のシフト状態に設定されている*呼び出すため*が指定されていません。

(size_t)(-2)次*カウント*バイトは、不完全ながら有効マルチバイト文字とそのすべてに貢献*カウント*バイトが処理されています。 値は格納されません*wchar*が*呼び出すため*関数を再開するように更新します。

## <a name="remarks"></a>Remarks

場合*mbchar* null ポインターの場合は、関数が呼び出しに相当します。

`mbrtowc(NULL, "", 1, &mbstate)`

この例では、引数の値で*wchar*と*カウント*は無視されます。

場合*mbchar* null ポインターでない関数は*カウント*からバイト*mbchar*必要な次の完了に必要なバイト数を決定するにはマルチバイト文字。 対応するマルチバイト文字が格納されている場合は、次の文字が有効な*wchar* null ポインターでない場合。 文字が、対応するワイド null 文字の結果の状態*呼び出すため*は初期の変換状態です。

**Mbrtowc**関数とは異なります[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)によってその再起動します。 変換の状態が格納されている*呼び出すため*同じか、またはその他の再開可能な関数を呼び出すのためです。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば、アプリケーションで使用する**後**の代わりに**wcslen**場合、後続の呼び出し**wcsrtombs**の代わりに使用が**wcstombs**.

## <a name="example"></a>例

マルチバイト文字を対応するワイド文字に変換します。

```cpp
// crt_mbrtowc.cpp

#include <stdio.h>
#include <mbctype.h>
#include <string.h>
#include <locale.h>
#include <wchar.h>

#define BUF_SIZE 100

int Sample(char* szIn, wchar_t* wcOut, int nMax)
{
    mbstate_t   state = {0}; // Initial state
    size_t      nConvResult,
                nmbLen = 0,
                nwcLen = 0;
    wchar_t*    wcCur = wcOut;
    wchar_t*    wcEnd = wcCur + nMax;
    const char* mbCur = szIn;
    const char* mbEnd = mbCur + strlen(mbCur) + 1;
    char*       szLocal;

    // Sets all locale to French_Canada.1252
    szLocal = setlocale(LC_ALL, "French_Canada.1252");
    if (!szLocal)
    {
        printf("The fuction setlocale(LC_ALL, \"French_Canada.1252\") failed!\n");
        return 1;
    }

    printf("Locale set to: \"%s\"\n", szLocal);

    // Sets the code page associated current locale's code page
    // from a previous call to setlocale.
    if (_setmbcp(_MB_CP_SBCS) == -1)
    {
        printf("The fuction _setmbcp(_MB_CP_SBCS) failed!");
        return 1;
    }

    while ((mbCur < mbEnd) && (wcCur < wcEnd))
    {
        //
        nConvResult = mbrtowc(wcCur, mbCur, 1, &state);
        switch (nConvResult)
        {
            case 0:
            {  // done
                printf("Conversion succeeded!\nMultibyte String: ");
                printf(szIn);
                printf("\nWC String: ");
                wprintf(wcOut);
                printf("\n");
                mbCur = mbEnd;
                break;
            }

            case -1:
            {  // encoding error
                printf("The call to mbrtowc has detected an encoding error.\n");
                mbCur = mbEnd;
                break;
            }

            case -2:
            {  // incomplete character
                if   (!mbsinit(&state))
                {
                    printf("Currently in middle of mb conversion, state = %x\n", state);
                    // state will contain data regarding lead byte of mb character
                }

                ++nmbLen;
                ++mbCur;
                break;
            }

            default:
            {
                if   (nConvResult > 2) // The multibyte should never be larger than 2
                {
                    printf("Error: The size of the converted multibyte is %d.\n", nConvResult);
                }

                ++nmbLen;
                ++nwcLen;
                ++wcCur;
                ++mbCur;
            break;
            }
        }
    }

   return 0;
}

int main(int argc, char* argv[])
{
    char    mbBuf[BUF_SIZE] = "AaBbCc\x9A\x8B\xE0\xEF\xF0xXyYzZ";
    wchar_t wcBuf[BUF_SIZE] = {L''};

    return Sample(mbBuf, wcBuf, BUF_SIZE);
}
```

### <a name="sample-output"></a>出力例

```Output
Locale set to: "French_Canada.1252"
Conversion succeeded!
Multibyte String: AaBbCcÜïα∩≡xXyYzZ
WC String: AaBbCcÜïα∩≡xXyYzZ
```

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**mbrtowc**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
