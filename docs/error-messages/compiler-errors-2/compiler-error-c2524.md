---
description: 詳細については、「コンパイラエラー C2524」を参照してください。
title: コンパイラ エラー C2524
ms.date: 11/04/2016
f1_keywords:
- C2524
helpviewer_keywords:
- C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
ms.openlocfilehash: 94e974674a5e244168499a50304a07264d23e618
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151139"
---
# <a name="compiler-error-c2524"></a>コンパイラ エラー C2524

' デストラクター ': デストラクターまたはファイナライザーには ' void ' パラメーターリストが必要です

デストラクターまたはファイナライザーに、 [void](../../cpp/void-cpp.md)ではないパラメーターリストがありました。 その他のパラメーターの型は使用できません。

## <a name="examples"></a>例

次のコードは、C2524 を再現します。

```cpp
// C2524.cpp
// compile with: /c
class A {
   A() {}
   ~A(int i) {}    // C2524
   // try the following line instead
   // ~A() {}
};
```

次のコードは、C2524 を再現します。

```cpp
// C2524_b.cpp
// compile with: /clr /c
ref struct I1 {
protected:
   !I1(int i);   // C2524
   // try the following line instead
   // !I1();
};
```
