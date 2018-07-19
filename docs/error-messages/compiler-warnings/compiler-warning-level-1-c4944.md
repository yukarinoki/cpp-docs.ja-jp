---
title: コンパイラの警告 (レベル 1) C4944 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4944
dev_langs:
- C++
helpviewer_keywords:
- C4944
ms.assetid: e2905eb1-2e3b-4fab-a48b-c0cae0fd997f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57ddad7aa383cfd6f8716d6b12fa56627c1ee0e0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290700"
---
# <a name="compiler-warning-level-1-c4944"></a>コンパイラの警告 (レベル 1) C4944
'symbol': 'assembly1' からシンボルをインポートできません: 'symbol' は既に現在のスコープに存在します  
  
 シンボルがソース コード ファイル内で定義されています。#using ステートメントはアセンブリを参照しますが、そのアセンブリもシンボルを定義しています。 アセンブリ内のシンボルは無視されます。  
  
## <a name="example"></a>例  
 ClassA という型を使用してコンポーネントを作成する例を次に示します。  
  
```  
// C4944.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
## <a name="example"></a>例  
 次の例では C4944 が生成されます。  
  
```  
// C4944b.cpp  
// compile with: /clr /W1  
class ClassA {  
public:  
   int u;  
};  
  
#using "C4944.dll"   // C4944 ClassA also defined C4944.dll  
  
int main() {  
   ClassA * x = new ClassA();  
   x->u = 9;  
   System::Console::WriteLine(x->u);  
}  
```