---
description: 詳細については、「コンパイラエラー C3084」を参照してください。
title: コンパイラ エラー C3084
ms.date: 11/04/2016
f1_keywords:
- C3084
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
ms.openlocfilehash: 8603930e9087f1e407d5e8df65078604836b9a16
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320120"
---
# <a name="compiler-error-c3084"></a>コンパイラ エラー C3084

'function': ファイナライザーまたはデストラクターを 'keyword' にすることはできません。

ファイナライザーまたはデストラクターの宣言が正しくありません。

たとえば、デストラクターをシール済みとしてマークすることはできません。  デストラクターは派生型にアクセスできません。  詳細については、「[方法: クラスと構造体を定義および使用する (C++/cli)」の](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)「[明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)とデストラクターおよびファイナライザー」を参照してください。

## <a name="example"></a>例

次の例では C3084 が生成されます。

```cpp
// C3084.cpp
// compile with: /clr /c
ref struct R {
protected:
   !R() sealed;   // C3084
   !R() abstract;   // C3084
   !R();
};
```
