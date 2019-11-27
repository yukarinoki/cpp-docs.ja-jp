---
title: コンパイラの警告 (レベル 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: 982457ded987f6aee4f2891bbb7d9103b830cc99
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541792"
---
# <a name="compiler-warning-level-4-c4238"></a>コンパイラの警告 (レベル 4) C4238

非標準の拡張機能が使用されています

以前のバージョンのビジュアルC++との互換性を保つために、Microsoft extensions ( **/ze**) では、暗黙的または明示的にアドレスを取得するコンテキストで、クラス型を右辺値として使用できます。 次の例のような場合は、これが危険になることがあります。

## <a name="example"></a>例

```cpp
// C4238.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

C * pC = &C();   // C4238
```

この使用法により、ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) でエラーが発生します。