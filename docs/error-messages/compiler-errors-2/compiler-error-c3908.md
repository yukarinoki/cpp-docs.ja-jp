---
description: 詳細については、「コンパイラエラー C3908」を参照してください。
title: コンパイラ エラー C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: 67258f9f5946d180af9a270b931f88f263238856
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144171"
---
# <a name="compiler-error-c3908"></a>コンパイラ エラー C3908

' construct ' よりも制限の緩いアクセスレベル

プロパティアクセサーメソッド (get または set) は、プロパティ自体で指定されたアクセスよりも制限が少ないアクセス許可を持つことはできません。  同様に、イベントアクセサーメソッドについても同様です。

詳細については、「 [プロパティ](../../extensions/property-cpp-component-extensions.md) と [イベント](../../extensions/event-cpp-component-extensions.md)」を参照してください。

次の例では、C3908 が生成されます。

```cpp
// C3908.cpp
// compile with: /clr
ref class X {
protected:
   property int i {
   public:   // C3908 property i is protected
      int get();
   private:
      void set(int);   // OK more restrictive
   };
};
```
