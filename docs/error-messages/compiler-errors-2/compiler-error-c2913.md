---
title: コンパイラ エラー C2913
ms.date: 11/04/2016
f1_keywords:
- C2913
helpviewer_keywords:
- C2913
ms.assetid: c6cf6090-02e8-49a5-913f-5bc6f864b769
ms.openlocfilehash: deeabdb08f4b0fb3cd722d5d33a4d2cfffb15d61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601572"
---
# <a name="compiler-error-c2913"></a>コンパイラ エラー C2913

明示的な特殊化です。'declaration' はクラス テンプレートの特殊化ではありません。

非テンプレート クラスを専門とすることはできません。

次の例では、C2913 が生成されます。

```
// C2913.cpp
// compile with: /c
class X{};
template <class T> class Y{};

template<> class X<int> {};   // C2913
template<> class Y<int> {};
```