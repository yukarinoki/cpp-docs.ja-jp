---
title: コンパイラ エラー C3292
ms.date: 11/04/2016
f1_keywords:
- C3292
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
ms.openlocfilehash: 7c59932a79534a365a20fcad25583f7addc0d624
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609609"
---
# <a name="compiler-error-c3292"></a>コンパイラ エラー C3292

cli 名前空間はを再度開くことはできません

コード内で cli 名前空間を宣言することはできません。  詳細については、次を参照してください。[プラットフォーム、既定では、および cli 名前空間](../../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では C3292 が生成されます。

```
// C3292.cpp
// compile with: /clr /c
namespace cli {};   // C3292
```