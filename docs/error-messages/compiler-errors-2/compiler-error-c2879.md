---
title: コンパイラ エラー C2879 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2879
dev_langs:
- C++
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 632142ea0efd8a9d009f18b898213cfa92514b16
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042477"
---
# <a name="compiler-error-c2879"></a>コンパイラ エラー C2879

'symbol': 既存の名前空間は、名前を指定できます、代替名前空間のエイリアス定義によってのみ

作成することはできません、[名前空間エイリアス](../../cpp/namespaces-cpp.md#namespace_aliases)名前空間以外のシンボルにします。

次の例では、C2879 が生成されます。

```
// C2879.cpp
int main() {
   int i;
   namespace A = i;   // C2879 i is not a namespace
}
```