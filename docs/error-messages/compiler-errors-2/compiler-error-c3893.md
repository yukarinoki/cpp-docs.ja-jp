---
title: コンパイラ エラー C3893 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3893
dev_langs:
- C++
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c95d44a90b9325a492a0f179c941d46ff24030c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273424"
---
# <a name="compiler-error-c3893"></a>コンパイラ エラー C3893
'var': initonly データ メンバーの左辺値の使用はクラス 'type_name' のインスタンス コンス トラクターでのみ許可  
  
 静的[initonly](../../dotnet/initonly-cpp-cli.md)データを持つメンバーにのみ、アドレスを静的コンス トラクターで取得します。  
  
 インスタンス (静的ではない) initonly データ メンバーは、インスタンス (静的ではない) コンス トラクターで、アドレスを与えるだけことができます。  
  
 次の例では、C3893 が生成されます。  
  
```  
// C3893.cpp  
// compile with: /clr  
ref struct Y1 {  
   Y1() : data_var(0) {  
      int% i = data_var;   // OK  
   }  
   initonly int data_var;  
};  
  
int main(){  
   Y1^ y= gcnew Y1;  
   int% i = y->data_var;   // C3893  
}  
```