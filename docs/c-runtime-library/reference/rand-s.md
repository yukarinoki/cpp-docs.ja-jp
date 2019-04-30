---
title: rand_s
ms.date: 1/02/2018
apiname:
- rand_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: d196a6f5d7483deb9a7e1b8d7fa929532b6197db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358126"
---
# <a name="rands"></a>rand_s

疑似乱数を生成します。 これは、関数のバージョンがより安全な[rand](rand.md)、セキュリティが強化された」の説明に従って[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)します。

## <a name="syntax"></a>構文

```C
errno_t rand_s(unsigned int* randomValue);
```

### <a name="parameters"></a>パラメーター

*randomValue*<br/>
生成された値を保持する整数へのポインター。

## <a name="return-value"></a>戻り値

正常に終了した場合は 0 を返し、それ以外の場合はエラー コードを返します。 場合、入力ポインター _randomValue_ null ポインターの場合は、」の説明に従って、関数は、無効なパラメーター ハンドラーを呼び出す[パラメーターの検証](../../c-runtime-library/parameter-validation.md)。 かどうかは、引き続き実行が許可された、関数を返します**EINVAL**設定と**errno**に**EINVAL**します。 その他の何らかの理由で、関数が失敗した場合 *_randomValue_は 0 に設定します。

## <a name="remarks"></a>Remarks

**Rand_s**関数は、0 ~ の範囲内で擬似乱数の整数を書き込みます**UINT_MAX**入力ポインターにします。 **Rand_s**関数は、オペレーティング システムを使用して、暗号強度が高い乱数を生成します。 によって生成されたシードを使用しない、 [srand](srand.md)関数で使用されるランダムな番号のシーケンスを影響[rand](rand.md)します。

**Rand_s**関数には、その定数が必要な **_CRT_RAND_S**インクルード ステートメント、関数を次の例のように、宣言の前に定義します。

```C
#define _CRT_RAND_S
#include <stdlib.h>
```

**rand_s**によって異なります、 [rtlgenrandom で](/windows/desktop/api/ntsecapi/nf-ntsecapi-rtlgenrandom)API で、Windows XP で使用でき、後でのみです。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
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

### <a name="sample-output"></a>出力例

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
