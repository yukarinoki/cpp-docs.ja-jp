---
title: コンパイラ エラー C2768 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2768
dev_langs:
- C++
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ee0fd3fa213639e70199cfe5653ee2034bc39b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233384"
---
# <a name="compiler-error-c2768"></a>コンパイラ エラー C2768
'function': 明示的なテンプレート引数の不正な使用  
  
 コンパイラは関数定義は関数テンプレートの明示的な特殊化であるはずだった場合、または関数の定義が、新しい関数になる場合を判断できませんでした。  
  
 このエラーは、Visual Studio .NET 2003 でコンパイラ準拠拡張機能の一部として導入されました。  
  
 次の例では、C2768 が生成されます。  
  
```  
// C2768.cpp  
template<typename T>  
void f(T) {}  
  
void f<int>(int) {}   // C2768  
  
// an explicit specialization  
template<>  
void f<int>(int) {}   
  
// global nontemplate function overload  
void f(int) {}  
```