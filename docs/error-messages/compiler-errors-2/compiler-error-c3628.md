---
description: 詳細については、「コンパイラエラー C3628」を参照してください。
title: コンパイラ エラー C3628
ms.date: 11/04/2016
f1_keywords:
- C3628
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
ms.openlocfilehash: ed0c434a40e6c513580e37b5fb2fc9f44b1dc5dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144405"
---
# <a name="compiler-error-c3628"></a>コンパイラ エラー C3628

' base class ': マネージクラスまたは WinRTclasses は、パブリック継承のみをサポートしています

マネージクラスまたは WinRT クラスを [プライベート](../../cpp/private-cpp.md) または [プロテクト](../../cpp/protected-cpp.md) 基底クラスとして使用しようとしました。 マネージクラスまたは WinRT クラスは、 [パブリック](../../cpp/public-cpp.md) アクセスを持つ基底クラスとしてのみ使用できます。

次の例は C3628 を生成し、その修正方法を示しています。

```cpp
// C3628a.cpp
// compile with: /clr
ref class B {
};

ref class D : private B {   // C3628

// The following line resolves the error.
// ref class D : public B {
};

int main() {
}
```
