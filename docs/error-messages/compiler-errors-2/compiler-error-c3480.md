---
title: コンパイラ エラー C3480 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3480
dev_langs:
- C++
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 673eff58b09fe1f2bbfe8a7629594399e8ca6b22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3480"></a>コンパイラ エラー C3480
'var': ラムダ キャプチャ変数は、外側の関数スコープの変数である必要があります  
  
 ラムダ キャプチャ変数が外側の関数スコープの変数ではありません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   ラムダ式のキャプチャ リストから変数を削除します。  
  
## <a name="example"></a>例  
 変数 `global` が外側の関数スコープではないため、次の例では C3480 が生成されます。  
  
```  
// C3480a.cpp  
  
int global = 0;  
int main()  
{  
   [&global] { global = 5; }(); // C3480  
}  
```  
  
## <a name="example"></a>例  
 次の例では、ラムダ式のキャプチャ リストから変数 `global` を削除することによって C3480 を解決しています。  
  
```  
// C3480b.cpp  
  
int global = 0;  
int main()  
{  
   [] { global = 5; }();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)