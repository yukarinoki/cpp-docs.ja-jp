---
title: コンパイラの警告 (レベル 1) C4002 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4002
dev_langs:
- C++
helpviewer_keywords:
- C4002
ms.assetid: 6bda1dfe-e2e4-4771-9794-5a404c466dd5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa1943000becde663fbb0da445f861f408f01f9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272013"
---
# <a name="compiler-warning-level-1-c4002"></a>コンパイラの警告 (レベル 1) C4002
マクロ 'identifier' に指定された実引数の数が多すぎます  
  
 マクロの実引数の数が、マクロ定義の仮引数の数を超えています。 余分な引数はプリプロセッサによって収集されますが、マクロの展開時には無視されます。  
  
 C4002 は、 [Variadic Macros](../../preprocessor/variadic-macros.md)が正しく使用されていない場合に発生する可能性があります。  
  
 次の例では C4002 が生成されます。  
  
```  
// C4002.cpp  
// compile with: /W1  
#define test(a) (a)  
  
int main() {  
   int a = 1;  
   int b = 2;  
   a = test(a,b);   // C4002  
   // try..  
   a = test(a);  
}  
```  
  
 このエラーは、マクロで余分なコンマを使用できない Visual Studio .NET 2003 でコンパイラ準拠作業が実施された結果、生成されることもあります。  
  
 コンパイラでは、マクロ内の余分なコンマが使用できなくなります。 Visual Studio .NET 2003 と Visual Studio .NET の両方のバージョンの Visual C++ でコードを有効にするには、余分なコンマを削除します。  
  
```  
// C4002b.cpp  
// compile with: /W1  
#define F(x,y)  
int main()  
{  
   F(2,,,,,,3,,,,,,)   // C4002  
   // Try the following line instead:  
   // F(2,3)  
}  
```