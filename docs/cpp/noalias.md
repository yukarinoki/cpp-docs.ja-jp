---
title: noalias |Microsoft ドキュメント
ms.custom: ''
ms.date: 02/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noalias_cpp
dev_langs:
- C++
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cbb5c1b4162f3326aade092c7e20ca42a825d13
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420120"
---
# <a name="noalias"></a>noalias

**Microsoft 固有の仕様**

`noalias` 関数呼び出しの変更または表示されるグローバル状態の参照はないことを意味が指すメモリのみを変更し、*直接*ポインター パラメーター (第 1 レベルの間接指定)。

関数が `noalias` として注釈が指定されている場合、オプティマイザーはパラメーター自体に加えてポインター パラメーターの第 1 レベルの間接指定のみが関数内で参照または変更されると仮定します。 表示されるグローバル状態は、コンパイルのスコープ外では、アドレスは取られません定義または参照されていないすべてのデータの設定です。 コンパイルのスコープは、すべてのソース ファイル ([/LTCG (リンク時コード生成)](../build/reference/ltcg-link-time-code-generation.md)ビルド) または 1 つのソース ファイル (非 **/LTCG**ビルド)。

`noalias`注釈は、注釈付きの関数の本体内でのみ適用されます。 関数としてマーク`__declspec(noalias)`関数によって返されるポインターのエイリアスには影響しません。

エイリアスに影響する別の注釈を参照してください。 [__declspec(restrict)](../cpp/restrict.md)です。

## <a name="example"></a>例

次の例では、使用する`__declspec(noalias)`です。

ときに、関数`multiply`アクセス メモリの注釈が付けられている`__declspec(noalias)`、この関数がパラメーター リストでポインターを使用してを除いてグローバル状態を変更していないことをコンパイラに伝えます。

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

[__declspec](../cpp/declspec.md)  
[キーワード](../cpp/keywords-cpp.md)  
[__declspec(restrict)](../cpp/restrict.md)  
