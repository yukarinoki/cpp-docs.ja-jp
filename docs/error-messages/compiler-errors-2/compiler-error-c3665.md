---
description: 詳細については、「コンパイラエラー C3665」を参照してください。
title: コンパイラ エラー C3665
ms.date: 11/04/2016
f1_keywords:
- C3665
helpviewer_keywords:
- C3665
ms.assetid: 893bb47e-8de1-43aa-af7d-fa47ad149ee9
ms.openlocfilehash: 3a4585361fa2ffab4835fafd47778a5c591bb001
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134278"
---
# <a name="compiler-error-c3665"></a>コンパイラ エラー C3665

'デコンストラクター' : オーバーライド指定子 'キーワード' は 'デコンストラクター/ファイナライザー' では使用できません

デストラクターまたはファイナライザーでは使用できないキーワードが使用されています。

たとえば、new スロットは、デストラクターまたはファイナライザーでは要求できません。  詳細については、「 [明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md) と [デストラクターおよびファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。

次の例では、C3665 が生成されます。

```cpp
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
