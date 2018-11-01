---
title: コンパイラ エラー C3238
ms.date: 11/04/2016
f1_keywords:
- C3238
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
ms.openlocfilehash: d81fd0fb3612a8c22fa6365aa7fc6dddb89cf120
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481160"
---
# <a name="compiler-error-c3238"></a>コンパイラ エラー C3238

'type' : この名前の型は、アセンブリ 'assembly' に既に転送されました

クライアント アプリケーションで定義された型は、参照されているアセンブリでも、型の転送構文によって定義されています。 アプリケーションのスコープで、両方の型を定義することはできません。

参照してください[Type Forwarding (C +/cli CLI)](../../windows/type-forwarding-cpp-cli.md)詳細についてはします。

## <a name="example"></a>例

次の例では、別のアセンブリから転送された型を含むアセンブリを作成します。

```
// C3238.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>例

次の例は型定義を含んでいたアセンブリを作成しますが、型の転送構文だけを含んでいるわけではありません。

```
// C3238_b.cpp
// compile with: /clr /LD
#using "C3238.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

## <a name="example"></a>例

次の例では C3238 が生成されます。

```
// C3238_c.cpp
// compile with: /clr /c
// C3238 expected
// Delete the following line to resolve.
#using "C3238_b.dll"
public ref class R {};
```