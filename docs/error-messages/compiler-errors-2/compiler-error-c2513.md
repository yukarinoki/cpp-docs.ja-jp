---
title: コンパイラ エラー C2513 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2513
dev_langs:
- C++
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 704e5d71301886d46c8a2ce08d7ea34ef1f8275a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2513"></a>コンパイラ エラー C2513
'type': '=' の前に変数が宣言されていません。  
  
 識別子のない変数宣言に型指定子が表示されます。  
  
 次の例では、C2513 が生成されます。  
  
```  
// C2513.cpp  
int main() {  
   int = 9;   // C2513  
   int i = 9;   // OK  
}  
```  
  
 このエラーは、Visual Studio .NET 2003 は実行コンパイラ準拠作業の結果として生成することもできます。 使用できなくなった typedef の初期化します。 Typedef の初期化は、標準では許可されていませんし、今すぐ、コンパイラ エラーを生成します。  
  
```  
// C2513b.cpp  
// compile with: /c  
typedef struct S {  
   int m_i;  
} S = { 1 };   // C2513  
// try the following line instead  
// } S;  
```  
  
 削除する方法もあります`typedef`、集計初期化子リストが、この変数の定義には使用しないでが型と同じ名前の変数を作成して、型名を非表示にするためです。