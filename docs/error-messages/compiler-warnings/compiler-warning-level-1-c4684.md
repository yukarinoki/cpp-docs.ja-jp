---
title: コンパイラの警告 (レベル 1) C4684
ms.date: 11/04/2016
f1_keywords:
- C4684
helpviewer_keywords:
- C4684
ms.assetid: e95f1a83-2784-4b05-ae94-12148e056e26
ms.openlocfilehash: 017d2ad9ac327e99bdd9afb0914d17946103771c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175455"
---
# <a name="compiler-warning-level-1-c4684"></a>コンパイラの警告 (レベル 1) C4684

' attribute ': WARNING!! 属性により、無効なコード生成が発生する可能性があります: 使用に注意してください

通常は使用しない属性を使用しています。

次の例では、C4684 が生成されます。

```cpp
// C4684.cpp
// compile with: /W1 /LD
[module(name="xx")]; // C4684 expected
[no_injected_text];
```
