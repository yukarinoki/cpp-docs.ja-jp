---
title: コンパイラの警告 (レベル 1) C4269 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4269
dev_langs:
- C++
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e393c657e12f84d3cadfacd469e35e3472a39d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281792"
---
# <a name="compiler-warning-level-1-c4269"></a>コンパイラの警告 (レベル 1) C4269
'identifier': 'const' で自動データ初期化コンパイラによって生成された既定のコンス トラクターには、信頼性のない結果が生成されます  
  
 A **const**コンパイラによって生成された既定のコンス トラクターを持つ重要なクラスの自動インスタンスを初期化します。  
  
## <a name="example"></a>例  
  
```  
// C4269.cpp  
// compile with: /c /LD /W1  
class X {  
public:  
   int m_data;  
};  
  
void g() {  
   const X x1;   // C4269  
};  
```  
  
 クラスのこのインスタンスは、スタックの初期値に生成されてから`m_data`何でもかまいません。 また、以降は、 **const**の値をインスタンス`m_data`は変更不可能です。