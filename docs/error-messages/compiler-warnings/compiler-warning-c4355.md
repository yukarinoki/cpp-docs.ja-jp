---
title: コンパイラの警告 C4355
ms.date: 11/04/2016
f1_keywords:
- C4355
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
ms.openlocfilehash: 6b74c8dd5ce9860cb218d21790f12ba05e9be22f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151826"
---
# <a name="compiler-warning-c4355"></a>コンパイラの警告 C4355

'this' : ベース メンバー初期化リストで使用されました。

**この**ポインターが非静的メンバー関数内でのみ有効です。 基底クラスの初期化子リストで使用できません。

基底クラスのコンス トラクターとクラス メンバーのコンス トラクターが前に呼び出されます**この**コンス トラクター。 実際には、ポインターを渡された別のコンス トラクターに未構築のオブジェクトにしました。 その他のコンス トラクターは、メンバーにアクセスまたはこのメンバー関数を呼び出し、結果は定義できません。 使用しないようにする、**この**すべての構築が完了するまでのポインター。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4355 が生成されます。

```
// C4355.cpp
// compile with: /w14355 /c
#include <tchar.h>

class CDerived;
class CBase {
public:
   CBase(CDerived *derived): m_pDerived(derived) {};
   ~CBase();
   virtual void function() = 0;

   CDerived * m_pDerived;
};

class CDerived : public CBase {
public:
   CDerived() : CBase(this) {};   // C4355 "this" used in derived c'tor
   virtual void function() {};
};

CBase::~CBase() {
   m_pDerived -> function();
}

int main() {
   CDerived myDerived;
}
```