---
title: コンパイラ エラー C3836 |Microsoft ドキュメント
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
ms.openlocfilehash: 45a2eda2567e63771ed4c8919945e34ee41be1cb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3836"></a>コンパイラ エラー C3836
静的コンス トラクターはメンバー初期化子リストを取得できません。  
  
 マネージ クラスには、静的コンス トラクターを持つメンバー初期化リストを持つことはできません。 クラスの初期化、静的データ メンバーの初期化を実行する共通言語ランタイムによっては、静的クラス コンス トラクターが呼び出されます。  
  
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
