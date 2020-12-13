---
description: 詳細については、「コンパイラエラー C3292」を参照してください。
title: コンパイラ エラー C3292
ms.date: 11/04/2016
f1_keywords:
- C3292
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
ms.openlocfilehash: 5c20ae5a03fd6eab442384c91c3357c2d9edb214
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144691"
---
# <a name="compiler-error-c3292"></a>コンパイラ エラー C3292

cli 名前空間はを再度開くことはできません

コード内で cli 名前空間を宣言することはできません。  詳細については、「[プラットフォーム、既定、および cli 名前空間](../../extensions/platform-default-and-cli-namespaces-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では C3292 が生成されます。

```cpp
// C3292.cpp
// compile with: /clr /c
namespace cli {};   // C3292
```
