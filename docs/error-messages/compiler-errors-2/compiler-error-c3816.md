---
title: コンパイラ エラー C3816 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3816
dev_langs:
- C++
helpviewer_keywords:
- C3816
ms.assetid: 2e52cc7f-e31c-41a3-8d6f-9f5fab3648c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bfc0cf864caeefd5b19e3d40383724909575d4df
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115894"
---
# <a name="compiler-error-c3816"></a>コンパイラ エラー C3816

'declaration' が以前に宣言または定義には、異なるマネージまたは WinRTmodifier

事前宣言および実際の宣言では、属性の宣言に競合や不整合がないことが求められます。

次の例では、C3816 を生成し、その修正方法を示しています。

```
// C3816a.cpp
// compile with: /clr /c
class C1;
// try the following line instead
// ref class C1;

ref class C1{  // C3816, forward declaration does not use ref
};
```