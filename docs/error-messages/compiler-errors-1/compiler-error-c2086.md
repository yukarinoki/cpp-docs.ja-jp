---
title: コンパイラ エラー C2086 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2086
dev_langs:
- C++
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04f1a21c06adeeda5d9db428e984da51f06addb5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2086"></a>コンパイラ エラー C2086
'identifier': 再定義されています  
  
 識別子が 2 回以上定義されているか、後の宣言と前の 1 つは異なります。  
  
 C2086 は、C# の場合、参照先アセンブリをインクリメンタル ビルドの結果もできます。 このエラーを解決するには、c# アセンブリを再構築します。  
  
 次の例では、C2086 が生成されます。  
  
```  
// C2086.cpp  
main() {  
  int a;  
  int a;   // C2086 not an error in ANSI C  
}  
```