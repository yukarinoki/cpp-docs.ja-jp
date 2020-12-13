---
description: 詳細については、「コンパイラエラー C2870」を参照してください。
title: コンパイラ エラー C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: 74e7f2de5cfbb5aca6bd653f5711b989de4ef326
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333767"
---
# <a name="compiler-error-c2870"></a>コンパイラ エラー C2870

' name ': 名前空間定義は、ファイルスコープで、または別の名前空間定義のすぐ下に記述する必要があります

名前空間が正しく定義されて `name` いません。 名前空間は、ファイルスコープ (すべてのブロックおよびクラスの外側) または別の名前空間内で定義する必要があります。

次の例では、C2870 が生成されます。

```cpp
// C2870.cpp
// compile with: /c
int main() {
   namespace A { int i; };   // C2870
}
```
