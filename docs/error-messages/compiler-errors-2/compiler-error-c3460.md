---
description: 詳細については、「コンパイラエラー C3460」を参照してください。
title: コンパイラ エラー C3460
ms.date: 11/04/2016
f1_keywords:
- C3460
helpviewer_keywords:
- C3460
ms.assetid: adbf8775-10ca-4654-acdf-58dd765351cd
ms.openlocfilehash: ee5bcb2396586d965f16d80ef006301c7bcd784f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315882"
---
# <a name="compiler-error-c3460"></a>コンパイラ エラー C3460

'type': 転送できるのはユーザー定義型のみです

詳細については、「 [型の転送 (C++/cli)](../../extensions/type-forwarding-cpp-cli.md)」を参照してください。

## <a name="examples"></a>例

コンポーネントを作成する例を次に示します。

```cpp
// C3460.cpp
// compile with: /LD /clr
public ref class R {};
```

次の例では C3460 が生成されます。

```cpp
// C3460_b.cpp
// compile with: /clr /c
#using "C3460.dll"
[assembly:TypeForwardedTo(int::typeid)];   // C3460
[assembly:TypeForwardedTo(R::typeid)];
```
