---
title: コンパイラ エラー C2518 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2518
dev_langs:
- C++
helpviewer_keywords:
- C2518
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 202d93e4ff466ddb1509c3d30ad3a326c07d0861
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051153"
---
# <a name="compiler-error-c2518"></a>コンパイラ エラー C2518

キーワード 'keyword' の基底クラス リスト; が無効です。無視されます。

キーワード`class`と`struct`が基底クラス リストに表示されません。

次の例では、C2518 が生成されます。

```
// C2518.cpp
// compile with: /c
class B {};
class C : public class B {};   // C2518
class D: public B {};   // OK
```