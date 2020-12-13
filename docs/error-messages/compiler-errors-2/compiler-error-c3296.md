---
description: 詳細については、「コンパイラエラー C3296」を参照してください。
title: コンパイラ エラー C3296
ms.date: 11/04/2016
f1_keywords:
- C3296
helpviewer_keywords:
- C3296
ms.assetid: fc4c9dcd-16cf-4eee-a1ac-c43e7c29e443
ms.openlocfilehash: 18c4cd35cda096cbb9e335e30da8d0631d247f60
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144613"
---
# <a name="compiler-error-c3296"></a>コンパイラ エラー C3296

'property': この名前のプロパティが既に存在します

コンパイラは同じ名前の 1 つ以上のプロパティを見つけました。 1 つの型の各プロパティには、一意の名前が必要です。

詳細については、「 [property](../../extensions/property-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では C3296 が生成されます。

```cpp
// C3296.cpp
// compile with: /clr /c
using namespace System;

ref class R {
public:
   property int MyProp[int] { int get(int); }

   property String^ MyProp[int] { void set(int, String^); }   // C3296
};
```
