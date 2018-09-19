---
title: コンパイラ エラー C3283 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3283
dev_langs:
- C++
helpviewer_keywords:
- C3283
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0feaad0e0eb1b9dc5ee6c5b2f47e8f2a425b6d99
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096471"
---
# <a name="compiler-error-c3283"></a>コンパイラ エラー C3283

'type': インターフェイスにインスタンス コンストラクターを含めることはできません

CLR [インターフェイス](../../windows/interface-class-cpp-component-extensions.md) にインスタンス コンストラクターを含めることはできません。  静的コンストラクターが許可されます。

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