---
description: 詳細については、「コンパイラエラー C3247」を参照してください。
title: コンパイラ エラー C3247
ms.date: 11/04/2016
f1_keywords:
- C3247
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
ms.openlocfilehash: 02e8f20f9804067e0179f3b5583d589d16dae302
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307189"
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
