---
title: コンパイラ エラー C3461
ms.date: 11/04/2016
f1_keywords:
- C3461
helpviewer_keywords:
- C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
ms.openlocfilehash: a674ce7819c88dd4e26355c0129a6c181da5c276
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781953"
---
# <a name="compiler-error-c3461"></a>コンパイラ エラー C3461

'type': マネージド型のみ転送できます

型の転送は、CLR 型でのみ実行できます。  参照してください[クラスと構造体](../../extensions/classes-and-structs-cpp-component-extensions.md)詳細についてはします。

詳細については、[Type Forwarding (C +/cli CLI)](../../extensions/type-forwarding-cpp-cli.md)を参照してください。

## <a name="example"></a>例

コンポーネントを作成する例を次に示します。

```
// C3461.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>例

次の例では C3461 が生成されます。

```
// C3461b.cpp
// compile with: /clr /c
#using "C3461.dll"
class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3461
[assembly:TypeForwardedTo(R::typeid)];   // OK
```