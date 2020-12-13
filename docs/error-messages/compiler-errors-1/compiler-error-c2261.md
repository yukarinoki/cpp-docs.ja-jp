---
description: 詳細については、「コンパイラエラー C2261」を参照してください。
title: コンパイラ エラー C2261
ms.date: 11/04/2016
f1_keywords:
- C2261
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
ms.openlocfilehash: c5156a240696f9021613b54cf7013e9372a13b45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134616"
---
# <a name="compiler-error-c2261"></a>コンパイラ エラー C2261

' string ': アセンブリ参照は無効であるため、解決できません

値が無効です。

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> は、フレンドアセンブリを指定するために使用されます。 たとえば、a.dll がフレンドアセンブリとして b.dll を指定する場合は、(a.dll): InternalsVisibleTo ("b") を指定します。 次に、ランタイムは、a.dll (プライベート型を除く) のすべてにアクセスする b.dll を許可します。

フレンドアセンブリを指定するときの正しい構文の詳細については、「 [フレンドアセンブリ (C++)](../../dotnet/friend-assemblies-cpp.md)」を参照してください。

## <a name="example"></a>例

次の例では、C2261 が生成されます。

```cpp
// C2261.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("a,a,a")];   // C2261
[assembly: InternalsVisibleTo("a.a")];   // OK
[assembly: InternalsVisibleTo("a")];   // OK
```
