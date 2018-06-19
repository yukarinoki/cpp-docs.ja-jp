---
title: コンパイラの警告 (レベル 1) C4286 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4286
dev_langs:
- C++
helpviewer_keywords:
- C4286
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2dab6c5c28809108e178ec7792a68a570ece14ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277115"
---
# <a name="compiler-warning-level-1-c4286"></a>コンパイラの警告 (レベル 1) C4286
'type1': 行番号の基本クラス ('type2') によってキャッチされました  
  
 指定された例外の種類は、以前のハンドラーによって処理されます。 2 番目の catch の型は、最初の型から派生します。 基本クラスの例外は、派生クラスで例外をキャッチします。  
  
## <a name="example"></a>例  
  
```  
//C4286.cpp  
// compile with: /W1  
#include <eh.h>  
class C {};  
class D : public  C {};  
int main()  
{  
    try  
    {  
        throw "ooops!";  
    }  
    catch( C ) {}  
    catch( D ) {}  // warning C4286, D is derived from C  
}  
```