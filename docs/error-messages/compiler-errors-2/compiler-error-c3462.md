---
description: 詳細については、「コンパイラエラー C3462」を参照してください。
title: コンパイラ エラー C3462
ms.date: 11/04/2016
f1_keywords:
- C3462
helpviewer_keywords:
- C3462
ms.assetid: 56b75f35-9fad-42d9-a969-eeca5d709bec
ms.openlocfilehash: e201dc9d999438053d5fd8d70813360c28a534df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315791"
---
# <a name="compiler-error-c3462"></a>コンパイラ エラー C3462

'type': インポートされた型のみを転送することができます

TypeForwardedTo 属性は、参照されたメタデータ内の型に適用する必要があります。

詳細については、「 [型の転送 (C++/cli)](../../extensions/type-forwarding-cpp-cli.md)」を参照してください。

## <a name="examples"></a>例

コンポーネントを作成する例を次に示します。

```cpp
// C3462.cpp
// compile with: /clr /LD
public ref class R {};
```

次の例では C3462 が生成されます。

```cpp
// C3462b.cpp
// compile with: /clr /c
#using "C3462.dll"
ref class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3462
[assembly:TypeForwardedTo(R::typeid)];
```
