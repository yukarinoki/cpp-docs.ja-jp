---
description: 詳細については、「コンパイラエラー C3238」を参照してください。
title: コンパイラ エラー C3238
ms.date: 11/04/2016
f1_keywords:
- C3238
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
ms.openlocfilehash: d2900d8c00badb19edb16bb726eaf2ea503d4ef4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307380"
---
# <a name="compiler-error-c3238"></a>コンパイラ エラー C3238

'type' : この名前の型は、アセンブリ 'assembly' に既に転送されました

クライアント アプリケーションで定義された型は、参照されているアセンブリでも、型の転送構文によって定義されています。 アプリケーションのスコープで、両方の型を定義することはできません。

詳細については、「 [型の転送 (C++/cli)](../../extensions/type-forwarding-cpp-cli.md) 」を参照してください。

## <a name="examples"></a>例

次の例では、別のアセンブリから転送された型を含むアセンブリを作成します。

```cpp
// C3238.cpp
// compile with: /clr /LD
public ref class R {};
```

次の例は型定義を含んでいたアセンブリを作成しますが、型の転送構文だけを含んでいるわけではありません。

```cpp
// C3238_b.cpp
// compile with: /clr /LD
#using "C3238.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

次の例では C3238 が生成されます。

```cpp
// C3238_c.cpp
// compile with: /clr /c
// C3238 expected
// Delete the following line to resolve.
#using "C3238_b.dll"
public ref class R {};
```
