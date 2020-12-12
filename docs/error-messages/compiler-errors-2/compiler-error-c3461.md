---
description: 詳細については、「コンパイラエラー C3461」を参照してください。
title: コンパイラ エラー C3461
ms.date: 11/04/2016
f1_keywords:
- C3461
helpviewer_keywords:
- C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
ms.openlocfilehash: 6158e0d6d38290a1925beba89fe77cba8f01c87b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113494"
---
# <a name="compiler-error-c3461"></a>コンパイラ エラー C3461

'type': マネージド型のみ転送できます

型の転送は、CLR 型でのみ実行できます。  詳細については [、「クラスと構造体](../../extensions/classes-and-structs-cpp-component-extensions.md) 」を参照してください。

詳細については、「 [型の転送 (C++/cli)](../../extensions/type-forwarding-cpp-cli.md)」を参照してください。

## <a name="examples"></a>例

コンポーネントを作成する例を次に示します。

```cpp
// C3461.cpp
// compile with: /clr /LD
public ref class R {};
```

次の例では C3461 が生成されます。

```cpp
// C3461b.cpp
// compile with: /clr /c
#using "C3461.dll"
class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3461
[assembly:TypeForwardedTo(R::typeid)];   // OK
```
