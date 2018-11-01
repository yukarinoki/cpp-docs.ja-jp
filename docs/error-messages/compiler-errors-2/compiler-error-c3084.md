---
title: コンパイラ エラー C3084
ms.date: 11/04/2016
f1_keywords:
- C3084
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
ms.openlocfilehash: 7659c17d999a8720ffb0ccdcdb631b27949167b7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572680"
---
# <a name="compiler-error-c3084"></a>コンパイラ エラー C3084

'function': ファイナライザーまたはデストラクターを 'keyword' にすることはできません。

ファイナライザーまたはデストラクターの宣言が正しくありません。

たとえば、デストラクターをシール済みとしてマークすることはできません。  デストラクターは派生型にアクセスできません。  詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)と[する方法のデストラクターおよびファイナライザー: クラスと構造体定義および使用 (C +/cli CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)します。

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