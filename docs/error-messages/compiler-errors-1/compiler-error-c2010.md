---
description: 詳細については、「コンパイラエラー C2010」を参照してください。
title: コンパイラエラー C2010
ms.date: 11/04/2016
f1_keywords:
- C2010
helpviewer_keywords:
- C2010
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
ms.openlocfilehash: 8a96c30103d46c23f3b678a2fa84abf34445dd11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221034"
---
# <a name="compiler-error-c2010"></a>コンパイラエラー C2010

' character ': マクロの仮パラメーターリストの中に予期しないものがあります。

マクロ定義の仮パラメーター リストの中で、文字が正しくない方法で使用されています。 エラーを解決するには、文字を削除します。

次の例では、C2010 が生成されます。

```cpp
// C2010.cpp
// compile with: /c
#define mymacro(a|) (2*a)   // C2010
#define mymacro(a) (2*a)   // OK
```
