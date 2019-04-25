---
title: コンパイラ エラー C3003
ms.date: 11/04/2016
f1_keywords:
- C3003
helpviewer_keywords:
- C3003
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
ms.openlocfilehash: 6d15d8bde8855b8dcc4857492acdeb950731b503
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152502"
---
# <a name="compiler-error-c3003"></a>コンパイラ エラー C3003

' directive':OpenMP ディレクティブ名は、ディレクティブ句の後に許可されていません

OpenMP ディレクティブの名前は、OpenMP ディレクティブの句の後に続けることはできません。

次の例では C3003 が生成されます。

```
// C3003.c
// compile with: /openmp
int main()
{
   int x, y, z;
   #pragma omp parallel shared(x, y, z) for   // C3003
}
```