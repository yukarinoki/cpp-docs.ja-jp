---
title: コンパイラ エラー C3533 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3533
dev_langs:
- C++
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f184f0459e7ec2251d6ff34e2ee76559fe0dea42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3533"></a>コンパイラ エラー C3533
'type': パラメーターは 'auto' を含む型を持つことはできません  
  
 メソッドまたはテンプレート パラメーターを宣言することはできません、`auto`キーワード場合、既定[/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md)コンパイラ オプションが有効にします。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  削除、`auto`パラメーターの宣言からキーワード。  
  
## <a name="example"></a>例  
 関数パラメーターを宣言しているために、次の例で C3535、`auto`キーワードとそれをコンパイルした **/Zc:auto**です。  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j){} // C3533  
```  
  
## <a name="example"></a>例  
 テンプレート パラメーターを宣言しているために、次の例で C3535、`auto`キーワードとそれをコンパイルした **/Zc:auto**です。  
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C{}; // C3533  
```  
  
## <a name="see-also"></a>関連項目  
 [auto キーワード](../../cpp/auto-keyword.md)   
 [/Zc:auto (変数の型の推測)](../../build/reference/zc-auto-deduce-variable-type.md)