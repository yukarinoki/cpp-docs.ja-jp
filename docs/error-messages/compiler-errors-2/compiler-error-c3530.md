---
title: コンパイラ エラー C3530 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3530
dev_langs:
- C++
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6514d655ab813ae21ecb440415f87bce63f3591
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253519"
---
# <a name="compiler-error-c3530"></a>コンパイラ エラー C3530
'auto' は、その他の型指定子と組み合わせることはできません。  
  
 型指定子を使用、`auto`キーワード。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  使用する変数宣言で型指定子を使用しない、`auto`キーワード。  
  
## <a name="example"></a>例  
 次の例では C3530 のため変数`x`が両方で宣言されて、`auto`キーワードと型`int`、例をコンパイルしたため、 **/Zc:auto**です。  
  
```  
// C3530.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto int x;   // C3530  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [auto キーワード](../../cpp/auto-keyword.md)