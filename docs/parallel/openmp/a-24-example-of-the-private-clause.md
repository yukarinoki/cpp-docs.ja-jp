---
title: プライベートの句の例を A.24 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f90a5b49-81ff-4746-ae03-37bbd33f6c08
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f8d07f2d95b565077f5dfd78fdc4ff6edf30216
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691389"
---
# <a name="a24---example-of-the-private-clause"></a>A.24 private 句の例
`private`句 ([セクション 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) [25] ページ) の並行領域のみが有効になって、領域の動的範囲ではなく、地域の構文の範囲に対するです。  そのため、変数の使用を次の例で *、* 内で、`for`ルーチンでループ*f*のプライベート コピーを指します *、*、一方で、使用方法ルーチン*g*グローバル *、* です。  
  
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