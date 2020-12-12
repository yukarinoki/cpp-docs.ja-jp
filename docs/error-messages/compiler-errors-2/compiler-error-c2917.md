---
description: 詳細については、「コンパイラエラー C2917」を参照してください。
title: コンパイラ エラー C2917
ms.date: 11/04/2016
f1_keywords:
- C2917
helpviewer_keywords:
- C2917
ms.assetid: ec9da9ee-0f37-47b3-87dd-19ef5a14dc4c
ms.openlocfilehash: c860ee47ae46db5667f39014b2f504f8f6d08e51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270434"
---
# <a name="compiler-error-c2917"></a>コンパイラ エラー C2917

'name' : 無効なテンプレートのパラメーターです。

テンプレートのパラメーター リストに、テンプレートのパラメーターでない識別子が含まれています。

## <a name="example"></a>例

次の例では C2917 が生成されます。

```cpp
// C2917.cpp
// compile with: /c
template<class T> class Vector {
   void sort();
};

template<class T*> void Vector<T>::sort() {}   // C2917
// try the following line instead
// template<class T> void Vector<T>::sort() {}
```
