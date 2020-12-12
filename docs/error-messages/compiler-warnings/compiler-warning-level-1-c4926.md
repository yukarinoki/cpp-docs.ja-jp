---
description: '詳細情報: コンパイラの警告 (レベル 1) C4926'
title: コンパイラの警告 (レベル 1) C4926
ms.date: 11/04/2016
f1_keywords:
- C4926
helpviewer_keywords:
- C4926
ms.assetid: 5717fce0-146f-4ef2-bde0-e9a01c0922d1
ms.openlocfilehash: 9b4f1d86085a5e0560237378728c2f267c44c780
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301894"
---
# <a name="compiler-warning-level-1-c4926"></a>コンパイラの警告 (レベル 1) C4926

'identifier': シンボルは既に定義されています。属性は無視されます。

事前宣言が見つかりましたが、同じ名前の属性付きコンストラクトが既に存在します。 事前宣言の属性は無視されます。

次の例では C4926 警告が生成されます。

```cpp
// C4926.cpp
// compile with: /W1
[module(name="MyLib")];

[coclass]
struct a {
};

[coclass]
struct a;   // C4926

int main() {
}
```
