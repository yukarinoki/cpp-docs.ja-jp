---
title: コンパイラ エラー C3255 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3255
dev_langs:
- C++
helpviewer_keywords:
- C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f77ad1530b59c01d36a7144e2074a4b1731a9db3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043483"
---
# <a name="compiler-error-c3255"></a>コンパイラ エラー C3255

'値の型': ネイティブ ヒープでこの値型のオブジェクトを動的に割り当てることはできません

値型のインスタンス (を参照してください[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)) メンバがマネージ ヒープではなく、スタック上に作成できます。

次の例では、C3255 が生成されます。

```
// C3255.cpp
// compile with: /clr
using namespace System;
value struct V {
   Object^ o;
};

value struct V2 {
   int i;
};

int main() {
   V* pv = new V;   // C3255
   V2* pv2 = new V2;
   V v2;
}
```
