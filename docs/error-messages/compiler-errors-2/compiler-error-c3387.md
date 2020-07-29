---
title: コンパイラ エラー C3387
ms.date: 11/04/2016
f1_keywords:
- C3387
helpviewer_keywords:
- C3387
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
ms.openlocfilehash: 8218233bb7a92c699952f7a506f6728386af4d17
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221069"
---
# <a name="compiler-error-c3387"></a>コンパイラ エラー C3387

' member ': __declspec (dllexport)/ \_ _declspec (dllimport) は、マネージ型または WinRT 型のメンバーには適用できません

`dllimport`および[dllexport](../../cpp/dllexport-dllimport.md)修飾子は、 **`__declspec`** マネージ型または Windows ランタイム型のメンバーでは無効です。

次の例では C3387 を生成し、その修正方法を示しています。

```cpp
// C3387a.cpp
// compile with: /clr /c
ref class X2 {
   void __declspec(dllexport) mf() {   // C3387
   // try the following line instead
   // void mf() {
   }
};
```
