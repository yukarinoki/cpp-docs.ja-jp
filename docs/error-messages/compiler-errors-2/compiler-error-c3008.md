---
description: 詳細については、「コンパイラエラー C3008」を参照してください。
title: コンパイラ エラー C3008
ms.date: 11/04/2016
f1_keywords:
- C3008
helpviewer_keywords:
- C3008
ms.assetid: 04d93201-28e5-4be0-945c-aad616376f4b
ms.openlocfilehash: 30ec8602ba9759eded7edc642931109216a68967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305339"
---
# <a name="compiler-error-c3008"></a>コンパイラ エラー C3008

'arg' : OpenMP 'directive' ディレクティブで、引数の終わりに ')' がありません

引数を受け取る OpenMP ディレクティブに、閉じかっこがありませんでした。

次の例では C3008 が生成されます。

```c
// C3008.c
// compile with: /openmp
int main()
{
   int x, y, z;
   #pragma omp parallel shared(x   // C3008
   // Try the following line instead:
   #pragma omp parallel shared(x)
   {
   }
}
```
