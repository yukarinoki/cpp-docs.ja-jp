---
description: 詳細については、「コンパイラエラー C3836」を参照してください。
title: コンパイラ エラー C3836
ms.date: 11/04/2016
f1_keywords:
- C3836
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
ms.openlocfilehash: c7e05bbf95facf5b8552b4442138cc38b86703c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180878"
---
# <a name="compiler-error-c3836"></a>コンパイラ エラー C3836

静的コンストラクターにメンバー初期化子リストを含めることはできません

マネージクラスは、メンバー初期化リストも持つ静的コンストラクターを持つことはできません。 静的クラスのコンストラクターは、静的データメンバーを初期化して、クラスの初期化を実行するために共通言語ランタイムによって呼び出されます。

## <a name="example"></a>例

次の例では、C3836 が生成されます。

```cpp
// C3836a.cpp
// compile with: /clr
ref class M
{
   static int s_i;

public:
   static M() :  s_i(1234)   // C3836, delete initializer to resolve
   {
   }
};

int main()
{
}
```
