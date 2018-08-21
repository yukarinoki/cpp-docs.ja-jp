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
ms.openlocfilehash: 6c08edff8237462cbc2c55dc5541e3da663ed0a3
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461114"
---
# <a name="return-statement-in-program-termination-c"></a>プログラム終了時の return ステートメント (C++)
発行、**返す**ステートメントから`main`呼び出しと同じ機能が、`exit`関数。 次に例を示します。  
  
```cpp 
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 `exit`と**返す**前の例のステートメントは機能的に同じです。 ただし、C++ を持つ関数が以外の型を返す必要**void**値を返します。 **返す**ステートメントを使用するから値を返す`main`します。  
  
## <a name="see-also"></a>関連項目  
 [プログラムの終了](../cpp/program-termination.md)