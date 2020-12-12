---
description: 詳細については、「コンパイラエラー C3152」を参照してください。
title: コンパイラエラー C3152
ms.date: 11/04/2016
f1_keywords:
- C3152
helpviewer_keywords:
- C3152
ms.assetid: 4ee6e2cd-5d19-4b73-833d-765c35797e4b
ms.openlocfilehash: b7e98535003a03ec5ac8b06d23b105d3727ff605
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322063"
---
# <a name="compiler-error-c3152"></a>コンパイラエラー C3152

'construct': 'keyword' はクラス、構造体、または仮想メンバー関数にのみ適用できます

特定のキーワードは、C++ クラスにのみ適用できます。

次の例では C3152 が生成され、その修正方法が示されています。

```cpp
// C3152.cpp
// compile with: /clr /c
ref class C {
   int (*pfn)() sealed;   // C3152
   virtual int g() sealed;   // OK
};
```
