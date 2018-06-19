---
title: 制限 |Microsoft ドキュメント
ms.custom: ''
ms.date: 02/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed5f91288671eaa3dcf4700ec35dae63ffaef172
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422889"
---
# <a name="restrict"></a>restrict

**Microsoft 固有の仕様**

関数宣言または関数ポインター型を返す定義に適用されるときに`restrict`関数ではないオブジェクトを返すことをコンパイラに指示*エイリアス*、つまり、他のポインターで参照します。 これにより、コンパイラの最適化を実行できます。

## <a name="syntax"></a>構文

> **__declspec(restrict)** *pointer_return_type* *function*();  
  
## <a name="remarks"></a>コメント

コンパイラに反映させる`__declspec(restrict)`です。 たとえば、CRT`malloc`関数には、`__declspec(restrict)`装飾、およびそのため、コンパイラは、によってメモリ位置へのポインターが初期化されていることを想定しています`malloc`はいないエイリアス化しても存在していたポインター。

コンパイラは、返されたポインターが実際に別名でがないことをチェックしません。 `restrict __declspec` 修飾子で示したポインターにエイリアスがないかどうか確認するのは開発者の責任です。  
  
変数によく似たセマンティクスは、次を参照してください。 [_ _restrict](../cpp/extension-restrict.md)です。
 
関数内ではエイリアスに適用される別の注釈を参照してください。[内](../cpp/noalias.md)です。
  
については、**制限**キーワードは C++ AMP の一部であるを参照してください[(C++ AMP) を制限する](../cpp/restrict-cpp-amp.md)です。  
 
## <a name="example"></a>例  

次の例では、使用する`__declspec(restrict)`です。

ときに`__declspec(restrict)`いるポインターを返す、このコンパイラは戻り値が指すメモリがエイリアス化されないこと関数に適用します。 この例では、ポインターで`mempool`と`memptr`グローバルには、コンパイラを参照しているメモリがエイリアス化されないことを確認することはできません。 ただし、内で使用された`ma`とその呼び出し元`init`をそれ以外の場合から参照されていない、プログラムでは、そのためメモリを返す方法で`__decslpec(restrict)`は、オプティマイザーに使用します。 これは、どの割り当て関数の装飾の CRT ヘッダーなどのような`malloc`を使用して`__declspec(restrict)`に必ず既存のポインターでエイリアス化することはできませんメモリを返すことを示すためにします。

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

[キーワード](../cpp/keywords-cpp.md)  
[__declspec](../cpp/declspec.md)  
[内](../cpp/noalias.md)  
