---
description: 詳細については、「コンパイラエラー C2605」を参照してください。
title: コンパイラエラー C2605
ms.date: 11/04/2016
f1_keywords:
- C2605
helpviewer_keywords:
- C2605
ms.assetid: a0e6f132-5acf-4e19-b277-ddf196d182bf
ms.openlocfilehash: e2aa86419b816cc48eecb9b981df73eeb3e48ccd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336239"
---
# <a name="compiler-error-c2605"></a>コンパイラエラー C2605

'name': このメソッドは、マネージド クラスまたは WinRT クラスで予約されています

内部関数用に、いくつかの名前がコンパイラによって予約されています。  詳細については、「 [デストラクターとファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。

## <a name="example"></a>例

次の例では C2605 が生成されます。

```cpp
// C2605.cpp
// compile with: /clr /c
ref class R {
protected:
   void Finalize() {}   // C2605
};
```
