---
title: コンパイラ エラー C2995 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2995
dev_langs:
- C++
helpviewer_keywords:
- C2995
ms.assetid: a57cdfe0-b40b-4a67-a95c-1a49ace4842b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5afd073e8877e2e28d5163d9c2e5ae72b9b7d4e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33242011"
---
# <a name="compiler-error-c2995"></a>コンパイラ エラー C2995
'function': 関数テンプレートは既に定義されています  
  
 テンプレート クラスの各メンバー関数の定義は 1 つのみであることを確認します。  
  
 次の例では C2995 が生成されます。  
  
```  
// C2995.cpp  
// compile with: /c  
template <class T>  
void Test(T x){}  
  
template <class T> void Test(T x){}   // C2995  
template <class T> void Test2(T x){}   // OK  
```