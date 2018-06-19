---
title: コンパイラ エラー C3633 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3633
dev_langs:
- C++
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 341123f51a065cc8dcd43425f65b21edaf00abbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267024"
---
# <a name="compiler-error-c3633"></a>コンパイラ エラー C3633
'member' をマネージ 'type' のメンバーとして定義できません。  
  
CLR 参照クラスのデータ メンバーは、POD C++ 以外の型のすることはできません。  POD ネイティブ型は CLR 型にインスタンス化することのみできます。  たとえば、POD 型では、コピー コンス トラクターまたは代入演算子を含めることはできません。  
  
## <a name="example"></a>例  
次の例では、C3633 を生成します。  
  
```  
// C3633.cpp  
// compile with: /clr /c  
#pragma warning( disable : 4368 )  
  
class A1 {  
public:  
   A1() { II = 0; }  
   int II;  
};  
  
ref class B {  
public:  
   A1 a1;   // C3633  
   A1 * a2;   // OK  
   B() : a2( new A1 ) {}  
    ~B() { delete a2; }  
};  
```  
