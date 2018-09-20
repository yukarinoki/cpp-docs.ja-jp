---
title: A.20 barrier ディレクティブのバインド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 628920caa6a122230f42394cc757e3abdb1874cd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381310"
---
# <a name="a20---binding-of-barrier-directives"></a>A.20 barrier ディレクティブのバインド

ディレクティブのバインディング ルールの呼び出しを**バリア**最も近い外側にバインドするディレクティブ`parallel`ディレクティブ。 ディレクティブのバインディングの詳細については、次を参照してください。[セクション 2.8](../../parallel/openmp/2-8-directive-binding.md) 32 ページ。

次の例からの呼び出しで*メイン*に*sub2*が準拠しているため、**バリア**(で*sub3*) 並列領域にバインドします*sub2*します。 呼び出しから*メイン*に*sub1*が準拠しているため、**バリア**サブルーチン内での並列領域にバインドします*sub2*。  呼び出しから*メイン*に*sub3*が準拠しているため、**バリア**並列の任意のリージョンにはバインドされません、無視されます。 また、**バリア**のみ、チームの外側の並列領域でスレッドとで作成されたすべてのスレッドを同期*sub1*します。

```
int main()
{
    sub1(2);
    sub2(2);
    sub3(2);
}

void sub1(int n)
{
    int i;
    #pragma omp parallel private(i) shared(n)
    {
        #pragma omp for
        for (i=0; i<n; i++)
            sub2(i);
    }
}

void sub2(int k)
{
     #pragma omp parallel shared(k)
     sub3(k);
}

void sub3(int n)
{
    work(n);
    #pragma omp barrier
    work(n);
}
```