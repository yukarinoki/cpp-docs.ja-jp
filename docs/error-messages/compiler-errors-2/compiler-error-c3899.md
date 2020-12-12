---
description: 詳細については、「コンパイラエラー C3899」を参照してください。
title: コンパイラ エラー C3899
ms.date: 11/04/2016
f1_keywords:
- C3899
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
ms.openlocfilehash: 04d8af9427d868b0890899d295f3aa6f678eafce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260047"
---
# <a name="compiler-error-c3899"></a>コンパイラ エラー C3899

' var ': initonly データメンバーの左辺値は、クラス ' class ' の並行領域内で直接使用することはできません

[Initonly (C++/cli)](../../dotnet/initonly-cpp-cli.md)データメンバーは、[並列](../../parallel/openmp/reference/openmp-directives.md#parallel)領域内のコンストラクターのその部分で初期化することはできません。  これは、コンパイラがそのコードの内部再配置を行うためです。そのため、実質的にはコンストラクターの一部ではなくなります。

解決するには、コンストラクターで initonly データメンバーを初期化しますが、並列領域の外側で初期化します。

## <a name="example"></a>例

次の例では、C3899 が生成されます。

```cpp
// C3899.cpp
// compile with: /clr /openmp
#include <omp.h>

public ref struct R {
   initonly int x;
   R() {
      x = omp_get_thread_num() + 1000;   // OK
      #pragma omp parallel num_threads(5)
      {
         // cannot assign to 'x' here
         x = omp_get_thread_num() + 1000;   // C3899
         System::Console::WriteLine("thread {0}", omp_get_thread_num());
      }
      x = omp_get_thread_num() + 1000;   // OK
   }
};

int main() {
   R^ r = gcnew R;
   System::Console::WriteLine(r->x);
}
```
