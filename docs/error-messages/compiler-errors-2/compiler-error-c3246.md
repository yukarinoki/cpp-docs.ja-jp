---
title: コンパイラ エラー C3246
ms.date: 11/04/2016
f1_keywords:
- C3246
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
ms.openlocfilehash: eb5ba268508922daf00adb49cf611c038db76343
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777446"
---
# <a name="compiler-error-c3246"></a>コンパイラ エラー C3246

'class': 'type' から継承できません。'sealed' として宣言されている理由によります。

[sealed](../../extensions/sealed-cpp-component-extensions.md) としてマークされているクラスは、他のクラスの基底クラスになることはできません。

次の例では C3246 が生成されます。

```
// C3246_2.cpp
// compile with: /clr /LD
ref class X sealed {};

ref class Y : public X {}; // C3246
```
