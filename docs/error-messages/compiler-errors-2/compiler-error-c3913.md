---
title: コンパイラ エラー C3913 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3913
dev_langs:
- C++
helpviewer_keywords:
- C3913
ms.assetid: a678bfce-9524-470d-9f23-7d08ecb972c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9b2ad0cc6bda9f46e3cf0a65de9e41b1808ac1f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098800"
---
# <a name="compiler-error-c3913"></a>コンパイラ エラー C3913

既定のプロパティのインデックスを作成する必要があります。

既定のプロパティの定義が正しくありません。

詳細については、「 [property](../../windows/property-cpp-component-extensions.md)」を参照してください。

次の例では、C3913 が生成されます。

```
// C3913.cpp
// compile with: /clr /c
ref struct X {
   property int default {   // C3913
   // try the following line instead
   // property int default[int] {
      int get(int) { return 0; }
      void set(int, int) {}
   }
};
```