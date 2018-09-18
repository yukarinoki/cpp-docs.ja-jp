---
title: コンパイラ エラー C2757 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2757
dev_langs:
- C++
helpviewer_keywords:
- C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ff853ad499a9d50cc1c5c168ac13a570453dcba
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058010"
---
# <a name="compiler-error-c2757"></a>コンパイラ エラー C2757

'symbol': この名前のシンボルが既に存在し、そのため、この名前は名前空間の名前として使用できません

名前空間の識別子として現在のコンパイルで使用されるシンボルは、参照アセンブリには既に使用されています。

次の例では、C2757 が生成されます。

```
// C2757a.cpp
// compile with: /clr /LD
public ref class Nes {};
```

この場合、次のようになります。

```
// C2757b.cpp
// compile with: /clr /c
#using <C2757a.dll>

namespace Nes {    // C2757
// try the following line instead
// namespace Nes2 {
   public ref class X {};
}
```
