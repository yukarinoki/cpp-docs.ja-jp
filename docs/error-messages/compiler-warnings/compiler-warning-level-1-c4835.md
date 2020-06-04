---
title: コンパイラの警告 (レベル 1) C4835
ms.date: 11/04/2016
f1_keywords:
- C4835
helpviewer_keywords:
- C4835
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
ms.openlocfilehash: f86fcaea8a742c19ce175a453c06669178ed2145
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174857"
---
# <a name="compiler-warning-level-1-c4835"></a>コンパイラの警告 (レベル 1) C4835

' variable ': マネージドコードがホストアセンブリで最初に実行されるまで、エクスポートされたデータの初期化子は実行されません

マネージコンポーネント間でデータにアクセスする場合は、ネイティブC++のインポートおよびエクスポートメカニズムを使用しないことをお勧めします。 代わりに、マネージ型内でデータメンバーを宣言し、クライアントで `#using` を使用してメタデータを参照します。 詳細については、「[#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4835 が生成されます。

```cpp
// C4835.cpp
// compile with: /W1 /clr /LD
int f() { return 1; }
int n = 9;

__declspec(dllexport) int m = f();   // C4835
__declspec(dllexport) int *p = &n;   // C4835
```

## <a name="example"></a>例

次の例では、前の例でビルドされたコンポーネントを使用して、変数の値が想定どおりでないことを示しています。

```cpp
// C4835_b.cpp
// compile with: /clr C4835.lib
#include <stdio.h>
__declspec(dllimport) int m;
__declspec(dllimport) int *p;

int main() {
   printf("%d\n", m);
   printf("%d\n", p);
}
```

```Output
0
268456008
```
