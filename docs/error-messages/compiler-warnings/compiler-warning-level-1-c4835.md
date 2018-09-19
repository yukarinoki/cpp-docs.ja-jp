---
title: コンパイラの警告 (レベル 1) C4835 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4835
dev_langs:
- C++
helpviewer_keywords:
- C4835
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70492be13d312c5d167990cfa0b6c0d741e1055f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080104"
---
# <a name="compiler-warning-level-1-c4835"></a>コンパイラの警告 (レベル 1) C4835

'variable': マネージ コードがホスト アセンブリで最初に実行されるまで、エクスポートされたデータの初期化子は実行されません

マネージ コンポーネント間のデータにアクセスするときは、こといないネイティブ C++ のインポートを使用しておよびエクスポートするメカニズムをお勧めします。 代わりに、マネージ型の内部で、データ メンバーを宣言し、メタデータを参照`#using`クライアント。 詳細については、「[#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4835 が生成されます。

```
// C4835.cpp
// compile with: /W1 /clr /LD
int f() { return 1; }
int n = 9;

__declspec(dllexport) int m = f();   // C4835
__declspec(dllexport) int *p = &n;   // C4835
```

## <a name="example"></a>例

次の例では、変数の値が予想どおりでないことを示す、前の例でビルドされたコンポーネントを使用します。

```
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