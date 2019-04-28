---
title: コンパイラ エラー C2757
ms.date: 11/04/2016
f1_keywords:
- C2757
helpviewer_keywords:
- C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
ms.openlocfilehash: 98b43a2f3c0888fc385226cd80889b9911c84690
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227915"
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
