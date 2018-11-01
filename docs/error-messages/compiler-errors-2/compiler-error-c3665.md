---
title: コンパイラ エラー C3665
ms.date: 11/04/2016
f1_keywords:
- C3665
helpviewer_keywords:
- C3665
ms.assetid: 893bb47e-8de1-43aa-af7d-fa47ad149ee9
ms.openlocfilehash: 30aaf67ac9f912059bb5726681e61feabc1e557d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644120"
---
# <a name="compiler-error-c3665"></a>コンパイラ エラー C3665

'デコンストラクター' : オーバーライド指定子 'キーワード' は 'デコンストラクター/ファイナライザー' では使用できません

デストラクターまたはファイナライザーでは使用できないキーワードが使用されています。

たとえば、new スロットは、デストラクターまたはファイナライザーでは要求できません。  詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)と[デストラクターおよびファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)します。

次の例では、C3665 が生成されます。

```
// C3665.cpp
// compile with: /clr
public ref struct R {
   virtual ~R() { }
   virtual void a() { }
};

public ref struct S : R {
   virtual ~S() new {}   // C3665
   virtual void a() new {}   // OK
};
```