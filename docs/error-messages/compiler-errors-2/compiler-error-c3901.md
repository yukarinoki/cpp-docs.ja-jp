---
title: コンパイラ エラー C3901 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3901
dev_langs:
- C++
helpviewer_keywords:
- C3901
ms.assetid: 19af4141-39ad-4c16-a68f-3ae76f648186
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7027b73c4d8899adb8b644fc52208780b996eab9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085577"
---
# <a name="compiler-error-c3901"></a>コンパイラ エラー C3901

'accessor_function': 戻り値の型 'type' があります。

少なくとも 1 つの get メソッドの戻り値の型は、プロパティの型と一致する必要があります。 詳細については、「 [property](../../windows/property-cpp-component-extensions.md)」を参照してください。

次の例では、C3901 が生成されます。

```
// C3901.cpp
// compile with: /clr /c
using namespace System;
ref class X {
   property String^ Name {
      void get();   // C3901
      // try the following line instead
      // String^ get();
   };
};

ref class Y {
   property double values[int, int] {
      int get(int, int);   // C3901
      // try the following line instead
      // double get(int, int);
   };
};
```