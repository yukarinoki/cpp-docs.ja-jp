---
title: コンパイラ エラー C3418 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3418
dev_langs:
- C++
helpviewer_keywords:
- C3418
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92147a636ff1b087134dd7c2d3fdbdb1398d5135
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3418"></a>コンパイラ エラー C3418
アクセス指定子 'specifier' はサポートされていません  
  
CLR アクセス指定子が正しく指定されていません。  詳細については、型の可視性とメンバーの可視性で参照してください[する方法: を定義して消費クラスと構造体 (C + + CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)です。  
  
## <a name="example"></a>例  
次の例では C3418 が生成されます。  
  
```cpp  
// C3418.cpp  
// compile with: /clr /c  
ref struct m {  
internal public:   // C3418  
   void test(){}  
};  
  
ref struct n {  
internal:   // OK  
   void test(){}  
};  
```