---
title: noalias
ms.date: 07/07/2020
f1_keywords:
- noalias_cpp
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
ms.openlocfilehash: 70c1f4e8bfa426e858014a78febc424b473a89ae
ms.sourcegitcommit: e17cc8a478b51739d67304d7d82422967b35f716
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "86127866"
---
# `noalias`

**Microsoft 固有の仕様**

**`noalias`** は、関数呼び出しが表示されているグローバル状態を変更または参照せず、ポインターパラメーターによって*直接*ポイントされているメモリのみを変更することを意味します (第1レベルの間接参照)。

関数にという注釈が付けられている場合 **`noalias`** 、オプティマイザーでは、パラメーター自体だけでは、ポインターパラメーターの最初のレベルの間接参照のみが関数内で参照または変更されると想定できます。

注釈は、 **`noalias`** 注釈付き関数の本体内でのみ適用されます。 関数をとしてマークしても、 **`__declspec(noalias)`** 関数によって返されるポインターの別名には影響しません。

別名に影響する可能性がある別の注釈については、「」を参照してください [`__declspec(restrict)`](../cpp/restrict.md) 。

## <a name="example"></a>例

の使用例を次に示し **`__declspec(noalias)`** ます。

`multiply`メモリにアクセスする関数に注釈が付けられると **`__declspec(noalias)`** 、この関数は、パラメーターリスト内のポインターを除き、グローバル状態を変更しないことをコンパイラに指示します。

```C
// declspec_noalias.c
#include <stdio.h>
#include <stdlib.h>

#define M 800
#define N 600
#define P 700

float * mempool, * memptr;

float * ma(int size)
{
    float * retval;
    retval = memptr;
    memptr += size;
    return retval;
}

float * init(int m, int n)
{
    float * a;
    int i, j;
    int k=1;

    a = ma(m * n);
    if (!a) exit(1);
    for (i=0; i<m; i++)
        for (j=0; j<n; j++)
            a[i*n+j] = 0.1/k++;
    return a;
}

__declspec(noalias) void multiply(float * a, float * b, float * c)
{
    int i, j, k;

    for (j=0; j<P; j++)
        for (i=0; i<M; i++)
            for (k=0; k<N; k++)
                c[i * P + j] =
                          a[i * N + k] *
                          b[k * P + j];
}

int main()
{
    float * a, * b, * c;

    mempool = (float *) malloc(sizeof(float) * (M*N + N*P + M*P));

    if (!mempool)
    {
        puts("ERROR: Malloc returned null");
        exit(1);
    }

    memptr = mempool;
    a = init(M, N);
    b = init(N, P);
    c = init(M, P);

    multiply(a, b, c);
}
```

## <a name="see-also"></a>関連項目

[`__declspec`](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[`__declspec(restrict)`](../cpp/restrict.md)
