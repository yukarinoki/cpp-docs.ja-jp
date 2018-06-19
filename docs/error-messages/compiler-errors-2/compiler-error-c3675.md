---
title: コンパイラ エラー C3675 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3675
dev_langs:
- C++
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b4aaa53ae1d92364fad143f127ee3e7b504acdd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273645"
---
# <a name="compiler-error-c3675"></a>コンパイラ エラー C3675
'function': 'property' が定義されているためには、予約されています  
  
 Get および set アクセサー メソッドと、コンパイラが生成単純なプロパティを宣言するときに名前が、プログラムのスコープ内に存在します。  コンパイラで生成された名前は、get _ と set _、プロパティ名に付加することによって形成されます。  そのため、コンパイラによって生成されたアクセサーと同じ名前を持つ関数を宣言できません。  
  
 詳細については、「 [property](../../windows/property-cpp-component-extensions.md) 」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C3675 を生成します。  
  
```  
// C3675.cpp  
// compile with: /clr /c  
ref struct C {  
public:  
   property int Size;  
   int get_Size() { return 0; }   // C3675  
};  
```