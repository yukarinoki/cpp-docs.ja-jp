---
description: 詳細については、「コンパイラエラー C2757」を参照してください。
title: コンパイラエラー C2757
ms.date: 11/04/2016
f1_keywords:
- C2757
helpviewer_keywords:
- C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
ms.openlocfilehash: e0be0f2a4c8dc5a5646400cbd0fa99e343ea82d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336192"
---
# <a name="compiler-error-c2757"></a>コンパイラエラー C2757

' symbol ': この名前のシンボルは既に存在するため、この名前を名前空間名として使用することはできません

現在のコンパイルで名前空間識別子として使用されているシンボルは、参照されたアセンブリで既に使用されています。

次の例では、C2757 が生成されます。

```cpp
// C2757a.cpp
// compile with: /clr /LD
public ref class Nes {};
```

この場合、次のようになります。

```cpp
// C2757b.cpp
// compile with: /clr /c
#using <C2757a.dll>

namespace Nes {    // C2757
// try the following line instead
// namespace Nes2 {
   public ref class X {};
}
```
