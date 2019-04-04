---
title: コンパイラ エラー C3468
ms.date: 11/04/2016
f1_keywords:
- C3468
helpviewer_keywords:
- C3468
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
ms.openlocfilehash: e3870fa21e2b4a932937edd49091980406a5ff0d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58777233"
---
# <a name="compiler-error-c3468"></a>コンパイラ エラー C3468

'type': 型は次のアセンブリにのみ転送できます:

'`file`' はアセンブリではありません

アセンブリ内の型のみを転送することができます。

詳細については、[Type Forwarding (C +/cli CLI)](../../extensions/type-forwarding-cpp-cli.md)を参照してください。

## <a name="example"></a>例

モジュールを作成する例を次に示します。

```
// C3468.cpp
// compile with: /LN /clr
public ref class R {};
```

## <a name="example"></a>例

次の例では C3468 が生成されます。

```
// C3468_b.cpp
// compile with: /clr /c
#using "C3468.netmodule"
[ assembly:TypeForwardedTo(R::typeid) ];   // C3468
```