---
title: コンパイラ エラー C3626 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3626
dev_langs:
- C++
helpviewer_keywords:
- C3626
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba6fb7c03c7c957999ca75e3946e4f78d290b78a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094703"
---
# <a name="compiler-error-c3626"></a>コンパイラ エラー C3626

'keyword': '_ _event' キーワードは、COM インターフェイス、メンバー関数、およびデリゲートへのポインターであるデータ メンバーにのみ使用できます

キーワードが正しく使用されていません。

次の例では、C3626 が生成されます。

```
// C3626.cpp
// compile with: /c
struct A {
   __event int i;   // C3626
// try the following line instead
// __event int i();
};
```