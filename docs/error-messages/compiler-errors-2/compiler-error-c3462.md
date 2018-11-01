---
title: コンパイラ エラー C3462
ms.date: 11/04/2016
f1_keywords:
- C3462
helpviewer_keywords:
- C3462
ms.assetid: 56b75f35-9fad-42d9-a969-eeca5d709bec
ms.openlocfilehash: 6c56e59be8bc4173c6568b47628f675ba4f4d782
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651777"
---
# <a name="compiler-error-c3462"></a>コンパイラ エラー C3462

'type': インポートされた型のみを転送することができます

TypeForwardedTo 属性は、参照されたメタデータ内の型に適用する必要があります。

詳細については、次を参照してください。 [Type Forwarding (C +/cli CLI)](../../windows/type-forwarding-cpp-cli.md)します。

## <a name="example"></a>例

コンポーネントを作成する例を次に示します。

```
// C3462.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>例

次の例では C3462 が生成されます。

```
// C3462b.cpp
// compile with: /clr /c
#using "C3462.dll"
ref class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3462
[assembly:TypeForwardedTo(R::typeid)];
```