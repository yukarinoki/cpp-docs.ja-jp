---
title: コンパイラ エラー C3247
ms.date: 11/04/2016
f1_keywords:
- C3247
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
ms.openlocfilehash: 7ca84b4f054852aefa75a9c4547286137b436c63
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569166"
---
# <a name="compiler-error-c3247"></a>コンパイラ エラー C3247

'class1': コクラスは他のコクラス 'class2' から継承できません

[coclass](../../windows/coclass.md) 属性でマークされたクラスは `coclass` 属性でマークされた別のクラスから継承できません。

次の例では C3247 が生成されます。

```
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