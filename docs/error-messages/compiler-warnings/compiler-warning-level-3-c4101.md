---
title: コンパイラの警告 (レベル 3) C4101 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4101
dev_langs:
- C++
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 973b966e4b589cb35ffc92da9031779b14d448e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4101"></a>コンパイラの警告 (レベル 3) C4101
'identifier': 参照されていないローカル変数  
  
 ローカル変数は使用されません。 この警告は、明らかな場合に発生します。  
  
```  
// C4101a.cpp  
// compile with: /W3  
int main() {  
int i;   // C4101  
}  
```  
  
 ただし、この警告がまた発生を呼び出すときに、**静的**メンバー関数は、クラスのインスタンスを経由します。  
  
```  
// C4101b.cpp  
// compile with:  /W3  
struct S {  
   static int func()  
   {  
      return 1;  
   }  
};  
  
int main() {  
   S si;   // C4101, si is never used  
   int y = si.func();  
   return y;  
}  
```  
  
 コンパイラはこのような状況で、に関する情報を使用して`si`にアクセスする、**静的**関数がクラスのインスタンスを呼び出すには必要ありません、**静的**関数です。 そのため、警告します。 この警告を解決するのには、次のことができます。  
  
-   インスタンス、コンパイラが使用して、コンス トラクターを追加`si`への呼び出しで`func`です。  
  
-   削除、**静的**キーワードの定義から`func`です。  
  
-   呼び出す、**静的**明示的に関数:`int y = S::func();`です。