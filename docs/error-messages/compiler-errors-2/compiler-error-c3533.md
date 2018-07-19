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
ms.openlocfilehash: faaf53d08512559b86c95148bc93e7b3367d2b01
ms.sourcegitcommit: 3bb7c1c0ceeb8012418e2fff9ae5a7db0fff3877
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2018
ms.locfileid: "34458915"
---
# <a name="compiler-error-c3533"></a>コンパイラ エラー C3533
'type': パラメーターは 'auto' を含む型を持つことはできません  
  
 メソッドまたはテンプレート パラメーターを宣言することはできません、`auto`キーワード場合、既定[/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md)コンパイラ オプションが有効にします。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  削除、`auto`パラメーターの宣言からキーワード。  
  
## <a name="example"></a>例  
 関数パラメーターを宣言しているために、次の例で C3533、`auto`キーワードとそれをコンパイルした **/Zc:auto**です。  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j) {} // C3533  
```  
  
## <a name="example"></a>例  
 次の例では C3533 c++ 14 モードでのテンプレート パラメーターを宣言しているため、`auto`キーワードとそれをコンパイルした **/Zc:auto**です。(C++ 17、これは推測される型の 1 つの非型テンプレート パラメーターを持つクラス テンプレートの有効な定義です。)
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C {}; // C3533  
```  
  
## <a name="see-also"></a>関連項目  
 [auto キーワード](../../cpp/auto-keyword.md)   
 [/Zc:auto (変数の型の推測)](../../build/reference/zc-auto-deduce-variable-type.md)
