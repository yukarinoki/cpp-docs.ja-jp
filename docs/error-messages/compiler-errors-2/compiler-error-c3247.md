---
title: コンパイラ エラー C3247
ms.date: 11/04/2016
f1_keywords:
- C3247
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
ms.openlocfilehash: 7ca84b4f054852aefa75a9c4547286137b436c63
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182484"
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