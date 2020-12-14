---
description: 詳細については、「コンパイラエラー C2766」を参照してください。
title: コンパイラエラー C2766
ms.date: 11/04/2016
f1_keywords:
- C2766
helpviewer_keywords:
- C2766
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
ms.openlocfilehash: bace06c6dc4392fa023317d9711005837d156aa2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239494"
---
# <a name="compiler-error-c2766"></a>コンパイラエラー C2766

明示的特殊化。' 特殊化 ' は既に定義されています

重複した明示的な特殊化は使用できません。 詳細については、「 [関数テンプレートの明示的な特殊化](../../cpp/explicit-specialization-of-function-templates.md)」を参照してください。

次の例では、C2766 が生成されます。

```cpp
// C2766.cpp
// compile with: /c
template<class T>
struct A {};

template<>
struct A<int> {};

template<>
struct A<int> {};   // C2766
// try the following line instead
// struct A<char> {};
```
