---
description: 詳細については、「コンパイラエラー C3622」を参照してください。
title: コンパイラ エラー C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: 19c599fced524001f360a4ad462a9dbebbfb2fa3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223036"
---
# <a name="compiler-error-c3622"></a>コンパイラ エラー C3622

' class ': ' keyword ' として宣言されたクラスはインスタンス化できません

[Abstract](../../extensions/abstract-cpp-component-extensions.md)としてマークされたクラスのインスタンスを作成しようとしました。 としてマーク **`abstract`** されたクラスは基底クラスにすることができますが、インスタンス化することはできません。

## <a name="example"></a>例

次の例では、C3622 が生成されます。

```cpp
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
