---
description: 詳細については、「コンパイラエラー C3467」を参照してください。
title: コンパイラ エラー C3467
ms.date: 11/04/2016
f1_keywords:
- C3467
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
ms.openlocfilehash: c00c78852380537d744c8d01681a921e487826df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113442"
---
# <a name="compiler-error-c3467"></a>コンパイラ エラー C3467

'type': この型は既に転送されました

同じ型の事前宣言が複数検出されました。 宣言は、型ごとに 1 回しかできません。

詳細については、「 [型の転送 (C++/cli)](../../extensions/type-forwarding-cpp-cli.md)」を参照してください。

## <a name="examples"></a>例

コンポーネントを作成する例を次に示します。

```cpp
// C3467.cpp
// compile with: /LD /clr
public ref class R {};
```

次の例では C3467 が生成されます。

```cpp
// C3467_b.cpp
// compile with: /clr /c
#using "C3467.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467
```
