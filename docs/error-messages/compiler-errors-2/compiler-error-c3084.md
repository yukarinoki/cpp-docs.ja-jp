---
title: コンパイラ エラー C3084
ms.date: 11/04/2016
f1_keywords:
- C3084
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
ms.openlocfilehash: 01e229fe0ae5bf9e04c577bb653ff1ed7fdb33bf
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "58773904"
---
# <a name="compiler-error-c3084"></a>コンパイラ エラー C3084

'function': ファイナライザーまたはデストラクターを 'keyword' にすることはできません。

ファイナライザーまたはデストラクターの宣言が正しくありません。

たとえば、デストラクターをシール済みとしてマークすることはできません。  デストラクターは派生型にアクセスできません。  詳細については、次を参照してください。[明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)と[する方法のデストラクターおよびファイナライザー。クラスと構造体定義および使用 (C +/cli CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)します。

## <a name="example"></a>例

次の例では C3084 が生成されます。

```
// C3084.cpp
// compile with: /clr /c
ref struct R {
protected:
   !R() sealed;   // C3084
   !R() abstract;   // C3084
   !R();
};
```