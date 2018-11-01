---
title: コンパイラ エラー C3468
ms.date: 11/04/2016
f1_keywords:
- C3468
helpviewer_keywords:
- C3468
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
ms.openlocfilehash: 185bd35bb732f592c75912fe69d4491252fe9d0b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476116"
---
# <a name="compiler-error-c3468"></a>コンパイラ エラー C3468

'type': 型は次のアセンブリにのみ転送できます:

'`file`' はアセンブリではありません

アセンブリ内の型のみを転送することができます。

詳細については、次を参照してください。 [Type Forwarding (C +/cli CLI)](../../windows/type-forwarding-cpp-cli.md)します。

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