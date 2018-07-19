---
title: コンパイラの警告 C4355 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4355
dev_langs:
- C++
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13f57b8a7c279b820f4f9fc4a68715804a12e625
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273807"
---
# <a name="compiler-warning-c4355"></a>コンパイラの警告 C4355
'this' : ベース メンバー初期化リストで使用されました。  
  
 **この**ポインターが非静的メンバー関数内でのみ有効です。 これは、基本クラスの初期化子リストで使用できません。  
  
 基底クラスのコンス トラクターおよびクラス メンバーのコンス トラクターは、前に呼び出されます**この**コンス トラクターです。 実際には、別のコンス トラクターに未構築のオブジェクトにポインターを渡さしました。 その他のコンス トラクターは、メンバーにアクセスまたはこのメンバー関数を呼び出し、結果は定義できません。 使用しないで、**この**すべての構築が完了するまでのポインター。  
  
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