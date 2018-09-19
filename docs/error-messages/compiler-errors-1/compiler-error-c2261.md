---
title: コンパイラ エラー C2261 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2261
dev_langs:
- C++
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed43dc43fb6ceaf514a8e7452b06eb7bdaf7362
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051647"
---
# <a name="compiler-error-c2261"></a>コンパイラ エラー C2261

'string': アセンブリ参照が有効でないし、解決することはできません

値が無効です。

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> フレンド アセンブリの指定に使用されます。 たとえば、a.dll b.dll をフレンド アセンブリとして指定する場合とで指定する (a.dll): InternalsVisibleTo("b") します。 ランタイムには、b.dll a.dll (プライベート型) を除くのすべてのアクセスが許可されます。

フレンド アセンブリを指定するときに、正しい構文の詳細は、次を参照してください。[フレンド アセンブリ (C++)](../../dotnet/friend-assemblies-cpp.md)します。

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