---
title: コンパイラ エラー C3628
ms.date: 11/04/2016
f1_keywords:
- C3628
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
ms.openlocfilehash: 581aae7e1f979b3dd39caf2ce3d263fdb856c56a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543777"
---
# <a name="compiler-error-c3628"></a>コンパイラ エラー C3628

'base class': マネージまたは WinRTclasses はパブリック継承のみをサポート

マネージまたは WinRT を使用しようとしたクラスとして、[プライベート](../../cpp/private-cpp.md)または[保護](../../cpp/protected-cpp.md)基本クラス。 マネージ配列または WinRT クラスを持つ基本クラスとしてのみ使用できます[パブリック](../../cpp/public-cpp.md)アクセスします。

次の例は C3628 を生成し、その修正方法を示しています。

```
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
