---
title: コンパイラ エラー C3039 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3039
dev_langs:
- C++
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b225103cf45331688a65d4528cadb39e730c75c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098096"
---
# <a name="compiler-error-c3039"></a>コンパイラ エラー C3039

'var' : OpenMP 'for' ステートメントのインデックス変数を減少変数にすることはできません

インデックス変数は暗黙的にプライベートであるため、囲む [parallel](../../parallel/openmp/reference/reduction.md) ディレクティブ内の [reduction](../../parallel/openmp/reference/parallel.md) 句で、変数を使用することはできません。

## <a name="example"></a>例

次の例では C3039 が生成されます。

```
// C3039.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel reduction(+: i)
   {
      #pragma omp for
      for (i = 0; i < 10; ++i)   // C3039
         g_i += i;
   }
}
```