---
title: コンパイラ エラー C3628 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3628
dev_langs:
- C++
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a65dc33c5381b063c3adb01072e930075108649
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037373"
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
