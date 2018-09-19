---
title: コンパイラ エラー C3769 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3769
dev_langs:
- C++
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da57a883bcf66535a531e98e23b5927d37cadccd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042229"
---
# <a name="compiler-error-c3769"></a>コンパイラ エラー C3769

'type': 入れ子になったクラスは、すぐ外側のクラスと同じ名前を持つことはできません

入れ子になったクラスは、すぐ外側のクラスと同じ名前を持つことはできません。

## <a name="example"></a>例

次の例では、C3769 が生成されます。

```
// C3769.cpp
// compile with: /c
class x {
   class x {};   // C3769
   class y {
      class x{};   // OK
   };
};
```