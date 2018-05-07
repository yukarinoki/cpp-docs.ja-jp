---
title: コンパイラ エラー C3481 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3481
dev_langs:
- C++
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77fc0f542a74cb077e59882e31dd1acb10c7b7e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3481"></a>コンパイラ エラー C3481
'var': ラムダ キャプチャ変数が見つかりません  
  
 コンパイラはラムダ式のキャプチャ リストに渡された変数の定義を見つけられませんでした。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   ラムダ式のキャプチャ リストから変数を削除します。  
  
## <a name="example"></a>例  
 次の例では、変数 `n` が定義されていないため、C3481 が生成されます。  
  
```  
// C3481.cpp  
  
int main()  
{  
   [n] {}(); // C3481  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)