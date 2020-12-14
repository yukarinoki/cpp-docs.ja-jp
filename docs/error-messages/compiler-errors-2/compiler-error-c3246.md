---
description: 詳細については、「コンパイラエラー C3246」を参照してください。
title: コンパイラ エラー C3246
ms.date: 11/04/2016
f1_keywords:
- C3246
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
ms.openlocfilehash: 5a74b642abe2e184e8e505ec1000433357de2522
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307195"
---
# <a name="compiler-error-c3246"></a>コンパイラ エラー C3246

'class': 'type' から継承できません。'sealed' として宣言されている理由によります。

[sealed](../../extensions/sealed-cpp-component-extensions.md) としてマークされているクラスは、他のクラスの基底クラスになることはできません。

次の例では C3246 が生成されます。

```cpp
// C3246_2.cpp
// compile with: /clr /LD
ref class X sealed {};

ref class Y : public X {}; // C3246
```
