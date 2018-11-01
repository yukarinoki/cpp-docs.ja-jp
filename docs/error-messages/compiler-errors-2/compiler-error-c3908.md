---
title: コンパイラ エラー C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: 84b21f20cbc8203a9cd70e487738c34c6ad3a89b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598928"
---
# <a name="compiler-error-c3908"></a>コンパイラ エラー C3908

'construct' よりもより制限の少ないアクセス レベル

プロパティ アクセサー メソッド (get または set) は、プロパティ自体に指定されたアクセスより緩いアクセスを持つことはできません。  同様に、イベント アクセサー メソッドの。

詳細については、次を参照してください。[プロパティ](../../windows/property-cpp-component-extensions.md)と[イベント](../../windows/event-cpp-component-extensions.md)します。

次の例では、C3908 が生成されます。

```
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