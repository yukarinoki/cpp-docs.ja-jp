---
title: コンパイラ エラー C3387
ms.date: 11/04/2016
f1_keywords:
- C3387
helpviewer_keywords:
- C3387
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
ms.openlocfilehash: bd783d9510b1699b33f108a4ce8d8c491028b758
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328706"
---
# <a name="compiler-error-c3387"></a>コンパイラ エラー C3387

'member': 関数/\__declspec(dllimport) は WinRT 型またはマネージのメンバーに適用できません

`dllimport`と[dllexport](../../cpp/dllexport-dllimport.md) `__declspec`修飾子は、管理対象のメンバーまたは Windows ランタイム型では有効でありません。

次の例では C3387 を生成し、その修正方法を示しています。

```
// C3387a.cpp
// compile with: /clr /c
ref class X2 {
   void __declspec(dllexport) mf() {   // C3387
   // try the following line instead
   // void mf() {
   }
};
```