---
title: コンパイラの警告 (レベル 4) C4670 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4670
dev_langs:
- C++
helpviewer_keywords:
- C4670
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9bec30fff715984073aa3061979fff11923f0bf8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33315361"
---
# <a name="compiler-warning-level-4-c4670"></a>コンパイラの警告 (レベル 4) C4670
'identifier': 基底クラスはアクセスできません  
  
 **try** ブロックでスローされる､指定されたオブジェクトの基底クラスにはアクセスできません。 オブジェクトがスローされる場合、そのオブジェクトはインスタンスを生成できません。 基底クラスが正しいアクセス指定子を使用して継承されているかどうかを確認してください。  
  
 次の例では C4670 警告が生成されます。  
  
```  
// C4670.cpp  
// compile with: /EHsc /W4  
class A  
{  
};  
  
class B : /* public */ A  
{  
} b;   // inherits A with private access by default  
  
int main()  
{  
    try  
    {  
       throw b;   // C4670  
    }  
    catch( B )  
    {  
    }  
}  
```