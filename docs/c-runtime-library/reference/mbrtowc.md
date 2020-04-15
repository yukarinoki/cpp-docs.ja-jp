---
title: mbrtowc
ms.date: 4/2/2020
api_name:
- mbrtowc
- _o_mbrtowc
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbrtowc
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
ms.openlocfilehash: be46c3f3c728b70c7cbf060572acc24662637a81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340927"
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

*Wchar*<br/>
変換されたワイド文字列を受け取るワイド文字のアドレス ( **wchar_t**と入力します ) 。 ワイド文字を返す必要がない場合、この値は null ポインターを指定できます。

*mbchar*<br/>
バイト シーケンスのアドレス (マルチバイト文字)。

*count*<br/>
チェックするバイト数。

*mbstate*<br/>
変換状態のオブジェクトへのポインター。 この値が null ポインターの場合、関数は静的な内部変換状態オブジェクトを使用します。 内部**mbstate_t**オブジェクトはスレッド セーフではないため、常に独自の*mbstate*引数を渡すことをお勧めします。

## <a name="return-value"></a>戻り値

次のいずれかの値:

0 次の*カウント*以下のバイト数は *、wchar*に格納されている null ワイド文字を表すマルチバイト文字を完了します *(wchar*が null ポインターでない場合)。

count*に*1 を含む 次の*カウント*以下のバイト数は、有効なマルチバイト文字を完了します。 返される値は、マルチバイト文字を完成するのに必要なバイト数です。 ワイド文字に相当する値は *、wchar*が null ポインタでない場合は*wchar*に格納されます。

(size_t)(-1)エンコード エラーが発生しました。 次の*カウント*数以下のバイト数は、完全で有効なマルチバイト文字に影響しません。 この場合 **、errno**は EILSEQ に設定され、変換シフト状態は*mbstate*で指定されていません。

(size_t)(-2)次の*カウント*バイトは、不完全だが有効な可能性のあるマルチバイト文字に影響し、すべての*カウント*バイトが処理されています。 *wchar*には値は格納されませんが、関数を再起動するために*mbstate*が更新されます。

## <a name="remarks"></a>解説

*mbchar*が null ポインターの場合、関数は呼び出しと等価です。

`mbrtowc(NULL, "", 1, &mbstate)`

この場合、引数*wchar*と*count*の値は無視されます。

*mbchar*が null ポインタでない場合、関数は*mbchar*からの*カウント*バイトを調べ、次のマルチバイト文字を完了するために必要なバイト数を判別します。 次の文字が有効な場合、対応するマルチバイト文字が null ポインターでない場合は *、wchar*に格納されます。 文字が対応するワイドヌル文字である場合 *、mbstate*の結果の状態は初期変換状態になります。

**mbrtowc**関数は、その再始動可能性によって[_mbtowc_lmbtowc](mbtowc-mbtowc-l.md)とは異なります。 変換状態は、同じ関数または他の再開可能な関数を呼び出す後続の呼び出しの場合は*mbstate*に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば、wcstombs の代わりに**wcsrtombs**への後続の呼び出しを使用する場合、アプリケーションは**wcslen**ではなく**wcsrlen**を使用**する**必要があります。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

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

### <a name="sample-output"></a>サンプル出力

```Output
Locale set to: "French_Canada.1252"
Conversion succeeded!
Multibyte String: AaBbCcÜïα∩≡xXyYzZ
WC String: AaBbCcÜïα∩≡xXyYzZ
```

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**mbrtowc**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
