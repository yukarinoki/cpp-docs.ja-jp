---
title: コンパイラ エラー C3467
ms.date: 11/04/2016
f1_keywords:
- C3467
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
ms.openlocfilehash: 70375950543b9525fca10fff3084c923095fa35e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "58780757"
---
# <a name="compiler-error-c3467"></a>コンパイラ エラー C3467

'type': この型は既に転送されました

同じ型の事前宣言が複数検出されました。 宣言は、型ごとに 1 回しかできません。

詳細については、次を参照してください。 [Type Forwarding (C +/cli CLI)](../../extensions/type-forwarding-cpp-cli.md)します。

## <a name="example"></a>例

コンポーネントを作成する例を次に示します。

```
// C3467.cpp
// compile with: /LD /clr
public ref class R {};
```

## <a name="example"></a>例

次の例では C3467 が生成されます。

```
// C3467_b.cpp
// compile with: /clr /c
#using "C3467.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467
```