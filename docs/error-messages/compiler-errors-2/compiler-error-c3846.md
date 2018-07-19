---
title: コンパイラ エラー C3846 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3846
dev_langs:
- C++
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97d5650d1743ba379ce065d4051bfed807a1df71
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268027"
---
# <a name="compiler-error-c3846"></a>コンパイラ エラー C3846
'symbol': 'assembly2' からシンボルをインポートできません: 'symbol' が既に別のアセンブリ 'assembly1' からインポートされると  
  
 以前に参照されたアセンブリからインポートされたために、参照されたアセンブリからシンボルをインポートできませんでした。  
  
## <a name="example"></a>例
次の例では、C3846 が生成されます。  
  
```  
// C3846a.cpp  
// compile with: /LD /clr  
public ref struct G  
{  
};  
```  
  
 これをコンパイルします。  
  
```  
// C3846b.cpp  
// compile with: /clr  
#using "c3846a.dll"  
#using "c3846a.obj"   // C3846  
  
int main()  
{  
}  
```  
