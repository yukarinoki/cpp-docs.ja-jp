---
title: コンパイラ エラー C3899
ms.date: 11/04/2016
f1_keywords:
- C3899
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
ms.openlocfilehash: 26860ba0e8fd92f491ee389147605ba82cecf25c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376030"
---
# <a name="compiler-error-c3899"></a>コンパイラ エラー C3899

'var': クラス 'class' で、並行領域内で直接 initonly データ メンバーの左辺値の使用が許可されていません

[Initonly (C +/cli CLI)](../../dotnet/initonly-cpp-cli.md)内にあるコンス トラクターの部分の内部データ メンバーを初期化することはできません、[並列](../../parallel/openmp/reference/parallel.md)リージョン。  これは、コンパイラは、そのコードの内部に従った再配置するため、コンス トラクターの一部では実質的になくなりました。

を解決するには、コンス トラクターが、並列領域外の initonly データ メンバーを初期化します。

## <a name="example"></a>例

次の例では、C3899 が生成されます。

```
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