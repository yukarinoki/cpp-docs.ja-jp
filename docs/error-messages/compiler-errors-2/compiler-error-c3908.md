---
title: コンパイラ エラー C3908 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3908
dev_langs:
- C++
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7591b8ab5f8495b6af866e23e7a169b0f9cd29a6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047318"
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