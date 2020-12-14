---
description: 詳細については、「コンパイラエラー C2005」を参照してください。
title: コンパイラエラー C2005
ms.date: 11/04/2016
f1_keywords:
- C2005
helpviewer_keywords:
- C2005
ms.assetid: 090530ed-e0ec-4358-833a-ca24260e7ffe
ms.openlocfilehash: 80ed80433d2e227b4c904d6ce4a68318feb98b05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298579"
---
# <a name="compiler-error-c2005"></a>コンパイラエラー C2005

\#行には行番号が必要ですが、' token ' が見つかりました

`#line`ディレクティブの後には、行番号を指定する必要があります。

次の例では、C2005 が生成されます。

```cpp
// C2005.cpp
int main() {
   int i = 0;
   #line i   // C2005
}
```

考えられる解決策:

```cpp
// C2005b.cpp
int main() {
   int i = 0;
   #line 0
}
```
