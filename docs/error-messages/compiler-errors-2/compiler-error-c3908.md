---
title: コンパイラ エラー C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: e11d830c3d662ea424caadeb50df669700f8c78f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778476"
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