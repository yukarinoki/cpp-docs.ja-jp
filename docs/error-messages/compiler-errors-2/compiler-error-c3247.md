---
title: コンパイラ エラー C3247
ms.date: 11/04/2016
f1_keywords:
- C3247
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
ms.openlocfilehash: c1b8aaddac32af4e0936ce7d45fbc59c3835dda2
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501389"
---
# <a name="compiler-error-c3247"></a>コンパイラ エラー C3247

'class1': コクラスは他のコクラス 'class2' から継承できません

[coclass](../../windows/attributes/coclass.md) 属性でマークされたクラスは `coclass` 属性でマークされた別のクラスから継承できません。

次の例では C3247 が生成されます。

```cpp
// C3247.cpp
[module(name="MyLib")];
[coclass]
class a {
};

[coclass]
class b : public a {   // C3247
};
int main() {
}
```
