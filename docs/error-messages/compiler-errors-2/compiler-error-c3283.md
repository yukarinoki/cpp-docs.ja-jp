---
title: コンパイラ エラー C3283
ms.date: 11/04/2016
f1_keywords:
- C3283
helpviewer_keywords:
- C3283
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
ms.openlocfilehash: 593b04b8593e261aa1980ada7693300b52a869c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381580"
---
# <a name="compiler-error-c3283"></a>コンパイラ エラー C3283

'type': インターフェイスにインスタンス コンストラクターを含めることはできません

CLR [インターフェイス](../../extensions/interface-class-cpp-component-extensions.md) にインスタンス コンストラクターを含めることはできません。  静的コンストラクターが許可されます。

次の例では C3283 が生成されます。

```
// C3283.cpp
// compile with: /clr
interface class I {
   I();   // C3283
};
```

考えられる解決方法:

```
// C3283b.cpp
// compile with: /clr /c
interface class I {
   static I(){}
};
```