---
description: 詳細については、「コンパイラエラー C2904」を参照してください。
title: コンパイラ エラー C2904
ms.date: 11/04/2016
f1_keywords:
- C2904
helpviewer_keywords:
- C2904
ms.assetid: d5802f2e-d3fc-473d-aa04-36957b4eaca5
ms.openlocfilehash: f49ff355a69fd0487e10de088e9a676f4b6981af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270694"
---
# <a name="compiler-error-c2904"></a>コンパイラ エラー C2904

'identifier': 名前は、現在のスコープで、テンプレートに対して使用されています。

重複する名前のコードを確認します。

次の例では C2904 が生成されます。

```cpp
// C2904.cpp
// compile with: /c
void X();  // X is declared as a function
template<class T> class X{};  // C2904
```
