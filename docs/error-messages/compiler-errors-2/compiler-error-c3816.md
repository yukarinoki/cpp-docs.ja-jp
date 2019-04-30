---
title: コンパイラ エラー C3816
ms.date: 11/04/2016
f1_keywords:
- C3816
helpviewer_keywords:
- C3816
ms.assetid: 2e52cc7f-e31c-41a3-8d6f-9f5fab3648c0
ms.openlocfilehash: d362480b3380fe4576ef56b8ca76dfa10eaa1408
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384284"
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