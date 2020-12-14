---
description: 詳細については、「コンパイラエラー C3612」を参照してください。
title: コンパイラ エラー C3612
ms.date: 11/04/2016
f1_keywords:
- C3612
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
ms.openlocfilehash: 332d4bae940a0c98b148fd6ba951a4f51d1bee27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223101"
---
# <a name="compiler-error-c3612"></a>コンパイラ エラー C3612

' type ': シールドクラスを抽象クラスにすることはできません

を使用して定義された型 `value` は既定でシールされます。基底クラスのすべてのメソッドを実装しない限り、クラスは抽象クラスです。 シールされた抽象クラスは基底クラスにすることも、インスタンス化することもできません。

詳細については、「[クラスと構造体](../../extensions/classes-and-structs-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3612 が生成されます。

```cpp
// C3612.cpp
// compile with: /clr /c
value struct V: public System::ICloneable {};   // C3612

// OK
value struct V2: public System::ICloneable {
   Object^ Clone();
};
```
