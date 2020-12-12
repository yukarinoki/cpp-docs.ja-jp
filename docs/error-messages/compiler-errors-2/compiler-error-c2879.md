---
description: 詳細については、「コンパイラエラー C2879」を参照してください。
title: コンパイラ エラー C2879
ms.date: 11/04/2016
f1_keywords:
- C2879
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
ms.openlocfilehash: 6060678f71bf36d0af2e94e380a046ea7916ef05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194372"
---
# <a name="compiler-error-c2879"></a>コンパイラ エラー C2879

' symbol ': 名前空間エイリアスの定義により、既存の名前空間に代替名を指定することはできません

名前空間以外のシンボルに対して [名前空間エイリアス](../../cpp/namespaces-cpp.md#namespace_aliases) を作成することはできません。

次の例では、C2879 が生成されます。

```cpp
// C2879.cpp
int main() {
   int i;
   namespace A = i;   // C2879 i is not a namespace
}
```
