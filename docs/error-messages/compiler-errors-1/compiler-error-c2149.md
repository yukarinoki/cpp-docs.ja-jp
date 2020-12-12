---
description: 詳細については、「コンパイラエラー C2149」を参照してください。
title: コンパイラ エラー C2149
ms.date: 11/04/2016
f1_keywords:
- C2149
helpviewer_keywords:
- C2149
ms.assetid: 7a106dab-d79f-41b9-85be-f36e86e4d2ab
ms.openlocfilehash: c93efe0648ebe064024177d61acd9d07150a1a1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235347"
---
# <a name="compiler-error-c2149"></a>コンパイラ エラー C2149

'identifier': 名前付きビットフィールドの幅が 0 です

名前を指定しない場合にのみ、ビット フィールドの幅を 0 にできます。

次の例では C2149 が生成されます。

```cpp
// C2149.cpp
// compile with: /c
struct C {
   int i : 0;   // C2149
   int j : 2;   // OK
};
```
