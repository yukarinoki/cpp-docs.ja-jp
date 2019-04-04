---
title: コンパイラ エラー C2261
ms.date: 11/04/2016
f1_keywords:
- C2261
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
ms.openlocfilehash: 2df788efd93fb531822d858ea5aee1722487db81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535747"
---
# <a name="compiler-error-c2261"></a>コンパイラ エラー C2261

'string': アセンブリ参照が有効でないし、解決することはできません

値が無効です。

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> フレンド アセンブリの指定に使用されます。 たとえば、a.dll b.dll をフレンド アセンブリとして指定する場合とで指定する (a.dll): InternalsVisibleTo("b") します。 ランタイムには、b.dll a.dll (プライベート型) を除くのすべてのアクセスが許可されます。

フレンド アセンブリを指定するときに、正しい構文の詳細は、[フレンド アセンブリ (C++)](../../dotnet/friend-assemblies-cpp.md)を参照してください。

## <a name="example"></a>例

次の例では、C2261 が生成されます。

```
// C2261.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("a,a,a")];   // C2261
[assembly: InternalsVisibleTo("a.a")];   // OK
[assembly: InternalsVisibleTo("a")];   // OK
```