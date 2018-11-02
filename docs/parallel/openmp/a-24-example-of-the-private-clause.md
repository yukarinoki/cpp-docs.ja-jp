---
title: A.24 private 句の例
ms.date: 11/04/2016
ms.assetid: f90a5b49-81ff-4746-ae03-37bbd33f6c08
ms.openlocfilehash: facf5b953b26d284f6bfed4f35a9162f6d2bf212
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552959"
---
# <a name="a24---example-of-the-private-clause"></a>A.24 private 句の例

`private`句 ([セクション 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) 25 ページ上)、並行領域の領域の動的範囲ではなく、リージョンの構文範囲に対する効果でのみが。  変数の使用を次の例ではそのため、 *、* 内で、`for`ルーチンでループ*f*のプライベート コピーを指す *、* での使用状況の中にルーチン*g*グローバル *、* します。

```
int a;

void f(int n)
{
    a = 0;

    #pragma omp parallel for private(a)
    for (int i=1; i<n; i++)
    {
        a = i;
        g(i, n);
        d(a);     // Private copy of "a"
        ...
    }
    ...

void g(int k, int n)
{
    h(k,a); // The global "a", not the private "a" in f
}
```