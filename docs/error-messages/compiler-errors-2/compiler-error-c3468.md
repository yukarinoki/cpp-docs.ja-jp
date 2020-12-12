---
description: 詳細については、「コンパイラエラー C3468」を参照してください。
title: コンパイラ エラー C3468
ms.date: 11/04/2016
f1_keywords:
- C3468
helpviewer_keywords:
- C3468
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
ms.openlocfilehash: 7e6d58e012baa0163f33867069e7250da61177b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315739"
---
# <a name="compiler-error-c3468"></a>コンパイラ エラー C3468

'type': 型は次のアセンブリにのみ転送できます:

'`file`' はアセンブリではありません

アセンブリ内の型のみを転送することができます。

詳細については、「 [型の転送 (C++/cli)](../../extensions/type-forwarding-cpp-cli.md)」を参照してください。

## <a name="examples"></a>例

モジュールを作成する例を次に示します。

```cpp
// C3468.cpp
// compile with: /LN /clr
public ref class R {};
```

次の例では C3468 が生成されます。

```cpp
// C3468_b.cpp
// compile with: /clr /c
#using "C3468.netmodule"
[ assembly:TypeForwardedTo(R::typeid) ];   // C3468
```
