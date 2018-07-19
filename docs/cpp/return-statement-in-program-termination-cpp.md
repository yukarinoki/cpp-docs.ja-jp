---
title: return ステートメントで、プログラムの終了 (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb594eb10e8068d5f5b3ed124d5e77b48ced728e
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943146"
---
# <a name="return-statement-in-program-termination-c"></a>プログラム終了時の return ステートメント (C++)
発行、`return`ステートメントから**メイン**呼び出しと同じ機能が、**終了**関数。 次に例を示します。  
  
```cpp 
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 **終了**と**返す**前の例のステートメントは機能的に同じです。 ただし、C++ を持つ関数が以外の型を返す必要**void**値を返します。 **返す**ステートメントを使用するから値を返す`main`します。  
  
## <a name="see-also"></a>関連項目  
 [プログラムの終了](../cpp/program-termination.md)