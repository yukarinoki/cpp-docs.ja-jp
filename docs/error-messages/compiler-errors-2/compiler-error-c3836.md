---
title: コンパイラ エラー C3836 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3836
dev_langs:
- C++
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a1349ff88c00f8091a8187bb963f4fb683b694e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046031"
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
