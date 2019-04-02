---
title: コンパイラ エラー C3363
ms.date: 11/04/2016
f1_keywords:
- C3363
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
ms.openlocfilehash: eca598233dbe4cae4730e952b45945653ec8ffaa
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775505"
---
# <a name="compiler-error-c3363"></a>コンパイラ エラー C3363

'type': 'typeid' のみを型に適用できます

[typeid](../../extensions/typeid-cpp-component-extensions.md) 演算子が正しく使用されていません。

## <a name="example"></a>例

次の例では C3363 が生成されます。

```
// C3363.cpp
// compile with: /clr
int main() {
   System::typeid;   // C3363
}
```