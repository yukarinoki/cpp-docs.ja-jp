---
title: rand_s
ms.date: 4/2/2020
api_name:
- rand_s
- _o_rand_s
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
- api-ms-win-crt-utility-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- rand_s
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, cryptographically secure
- random numbers, generating
- rand_s function
- numbers, pseudorandom
- cryptographically secure random numbers
- pseudorandom numbers
- numbers, generating pseudorandom
ms.openlocfilehash: b11a40dd9dc58964df77330767a55aa95a179319
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338204"
---
# <a name="rand_s"></a>rand_s

疑似乱数を生成します。 これは[、CRT](../../c-runtime-library/security-features-in-the-crt.md)のセキュリティ機能で説明されているように、セキュリティが強化された、より安全なバージョンの関数[rand](rand.md)です。

## <a name="syntax"></a>構文

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>パラメーター

*ランダム値*<br/>
生成された値を保持する整数へのポインター。

## <a name="return-value"></a>戻り値

正常に終了した場合は 0 を返し、それ以外の場合はエラー コードを返します。 入力ポインター _randomValue_が null ポインターの場合、関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、関数は**EINVAL**を返し **、errno**を**EINVAL**に設定します。 関数が失敗した場合、その他の理由で *_randomValue_は 0 に設定されます。

## <a name="remarks"></a>解説

**rand_s**関数は、0 から**UINT_MAX**までの範囲の擬似ランダム整数を入力ポインターに書き込みます。 **rand_s**関数は、暗号化された安全な乱数を生成するために、オペレーティング システムを使用します。 [srand](srand.md)関数によって生成されたシードを使用しません。 [rand](rand.md)

**rand_s**関数では **、次の**例のように、宣言する関数のインクルード ステートメントの前に定数を定義_CRT_RAND_S必要があります。

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#define _CRT_RAND_S
#include <stdlib.h>
```

**rand_s**は、Windows XP 以降でのみ使用できる[RtlGenRandom](/windows/win32/api/ntsecapi/nf-ntsecapi-rtlgenrandom) API に依存します。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**rand_s**|\<stdlib.h>|

詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_rand_s.c
// This program illustrates how to generate random
// integer or floating point numbers in a specified range.

// Remembering to define _CRT_RAND_S prior
// to inclusion statement.
#define _CRT_RAND_S

#include <stdlib.h>
#include <stdio.h>
#include <limits.h>

int main( void )
{
    int             i;
    unsigned int    number;
    double          max = 100.0;
    errno_t         err;

    // Display 10 random integers in the range [ 1,10 ].
    for( i = 0; i < 10;i++ )
    {
        err = rand_s( &number );
        if (err != 0)
        {
            printf_s("The rand_s function failed!\n");
        }
        printf_s( "  %u\n", (unsigned int) ((double)number /
                       ((double) UINT_MAX + 1 ) * 10.0) + 1);
    }

    printf_s("\n");

    // Display 10 random doubles in [0, max).
    for (i = 0; i < 10;i++ )
    {
        err = rand_s( &number );
        if (err != 0)
        {
            printf_s("The rand_s function failed!\n");
        }
        printf_s( "  %g\n", (double) number /
                          ((double) UINT_MAX + 1) * max );
    }
}
```

### <a name="sample-output"></a>サンプル出力

```Output
10
4
5
2
8
2
5
6
1
1

32.6617
29.4471
11.5413
6.41924
20.711
60.2878
61.0094
20.1222
80.9192
65.0712
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
[srand](srand.md)<br/>
