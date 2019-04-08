---
title: コンパイラ エラー C3292
ms.date: 11/04/2016
f1_keywords:
- C3292
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
ms.openlocfilehash: a68d3e922532480063fe4c294e40f453885743e8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "58780653"
---
# <a name="compiler-error-c3292"></a>コンパイラ エラー C3292

cli 名前空間はを再度開くことはできません

コード内で cli 名前空間を宣言することはできません。  詳細については、次を参照してください。[プラットフォーム、既定では、および cli 名前空間](../../extensions/platform-default-and-cli-namespaces-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では C3292 が生成されます。

```
// C3292.cpp
// compile with: /clr /c
namespace cli {};   // C3292
```