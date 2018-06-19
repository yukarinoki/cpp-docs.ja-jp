---
title: コンパイラ エラー C2753 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2753
dev_langs:
- C++
helpviewer_keywords:
- C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acbf5736c7c263293bc1c2782cab7df4f0af2083
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235364"
---
# <a name="compiler-error-c2753"></a>コンパイラ エラー C2753
'*テンプレート*': 部分的特殊化はプライマリ テンプレートの引数リストと一致ことはできません  
  
 テンプレート引数リストには、パラメーター リストが一致すると、コンパイラにより、同じテンプレートとして扱います。 同じテンプレートを 2 回定義することはできません。  
  
## <a name="example"></a>例
 次の例では、C2753 を生成し、その修正方法を示しています。  
  
```cpp  
// C2753.cpp  
// compile with: cl /c C2753.cpp
template<class T>  
struct A {};  
  
template<class T>  
struct A<T> {};   // C2753  
// try the following line instead  
// struct A<int> {};  
  
template<class T, class U, class V, class W, class X>  
struct B {};  
```