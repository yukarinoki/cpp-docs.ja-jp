---
description: '詳細情報: 制限'
title: restrict
ms.date: 02/09/2018
f1_keywords:
- restrict_cpp
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
ms.openlocfilehash: e2900e46d3b8e452661800c1c511418f936a5b0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223712"
---
# <a name="restrict"></a>restrict

**Microsoft 固有の仕様**

ポインター型を返す関数宣言または定義に適用された場合、は、その関数が、エイリアスが設定されて **`restrict`** いないオブジェクト、つまり他のポインターによって参照されているオブジェクトを返すことをコンパイラに指示します。  これにより、コンパイラは追加の最適化を実行できます。

## <a name="syntax"></a>構文

> **`__declspec(restrict)`***pointer_return_type* *関数*();

## <a name="remarks"></a>解説

コンパイラが伝達さ **`__declspec(restrict)`** れます。 たとえば、CRT 関数には装飾があるため、 `malloc` **`__declspec(restrict)`** コンパイラは、によってメモリ位置に初期化されたポインターが、 `malloc` 以前の既存のポインターによってエイリアス化されていないと見なします。

コンパイラは、返されたポインターが実際にエイリアス化されていないことを確認しません。 **制限 __declspec** 修飾子でマークされたポインターにプログラムがエイリアスを使用しないようにするのは、開発者の責任です。

変数に関する同様のセマンティクスについては、「 [__restrict](../cpp/extension-restrict.md)」を参照してください。

関数内の別名に適用される別の注釈については、「 [__declspec」 (noalias)](../cpp/noalias.md)を参照してください。

C++ AMP の一部であるキーワードの詳細について **`restrict`** は、「 [restrict (C++ AMP)](../cpp/restrict-cpp-amp.md)」を参照してください。

## <a name="example"></a>例

の使用例を次に示し **`__declspec(restrict)`** ます。

**`__declspec(restrict)`** ポインターを返す関数にが適用されると、戻り値が指すメモリがエイリアス化されていないことをコンパイラに通知します。 この例では、ポインター `mempool` と `memptr` はグローバルであるため、コンパイラは参照するメモリがエイリアス化されていないことを確認できません。 ただし、これらは `ma` プログラムによって参照されていないメモリを返すようにとの呼び出し元で使用される `init` ため、オプティマイザーを支援するために **__decslpec (restrict)** が使用されます。 これは、CRT ヘッダーが、を使用して、 `malloc` **`__declspec(restrict)`** 既存のポインターによってエイリアス化できないメモリを常に返すことを示すなどの割り当て関数を装飾する方法に似ています。

```C
// declspec_restrict.c
// Compile with: cl /W4 declspec_restrict.c
#include <stdio.h>
#include <stdlib.h>

#define M 800
#define N 600
#define P 700

float * mempool, * memptr;

__declspec(restrict) float * ma(int size)
{
    float * retval;
    retval = memptr;
    memptr += size;
    return retval;
}

__declspec(restrict) float * init(int m, int n)
{
    float * a;
    int i, j;
    int k=1;

    a = ma(m * n);
    if (!a) exit(1);
    for (i=0; i<m; i++)
        for (j=0; j<n; j++)
            a[i*n+j] = 0.1f/k++;
    return a;
}

void multiply(float * a, float * b, float * c)
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

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[__declspec](../cpp/declspec.md)<br/>
[__declspec (noalias)](../cpp/noalias.md)
