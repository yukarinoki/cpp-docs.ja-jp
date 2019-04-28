---
title: コンパイラ エラー C3836
ms.date: 11/04/2016
f1_keywords:
- C3836
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
ms.openlocfilehash: 33860273db07894a9a4d15ba6d578598a18819ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208058"
---
# <a name="compiler-error-c3836"></a>コンパイラ エラー C3836

メンバー初期化子の一覧がなくても静的コンス トラクターが許可されていません

マネージ クラスは、静的コンス トラクターを持つメンバーの初期化リストを含めることはできません。 静的クラスのコンス トラクターはクラスの初期化、静的データ メンバーの初期化を実行する共通言語ランタイムによって呼び出されます。

## <a name="example"></a>例

次の例では、C3836 が生成されます。

```
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
