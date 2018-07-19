---
title: コンパイラ エラー C2951 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2951
dev_langs:
- C++
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0883b0942fdfbe3d55a540fbed35a0affc73be5b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33241537"
---
# <a name="compiler-error-c2951"></a>コンパイラ エラー C2951
型宣言がグローバル、名前空間でのみ許可されますまたはクラス スコープ  
  
 ジェネリックまたはテンプレート クラスは、外部グローバルまたは名前空間のスコープを宣言することはできません。 インクルード ファイルで、ジェネリックまたはテンプレートの宣言を行った場合は、グローバル スコープでは、インクルード ファイルを確認します。  
  
 次の例では、C2951 が生成されます。  
  
```  
// C2951.cpp  
template <class T>  
class A {};  
  
int main() {  
   template <class T>   // C2951  
   class B {};  
}  
```  
  
 C2951 は、ジェネリックを使用するときにも発生することができます。  
  
```  
// C2951b.cpp  
// compile with: /clr /c  
  
// OK  
generic <class T>   
ref class GC { };  
  
int main() {  
   generic <class T> ref class GC2 {};   // C2951  
}  
```