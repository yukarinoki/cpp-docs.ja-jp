---
title: コンパイラ エラー C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: e11d830c3d662ea424caadeb50df669700f8c78f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406555"
---
# <a name="compiler-error-c3908"></a>コンパイラ エラー C3908

'construct' よりもより制限の少ないアクセス レベル

プロパティ アクセサー メソッド (get または set) は、プロパティ自体に指定されたアクセスより緩いアクセスを持つことはできません。  同様に、イベント アクセサー メソッドの。

詳細については、次を参照してください。[プロパティ](../../extensions/property-cpp-component-extensions.md)と[イベント](../../extensions/event-cpp-component-extensions.md)します。

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