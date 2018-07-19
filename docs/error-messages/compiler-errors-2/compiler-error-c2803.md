---
title: コンパイラ エラー C2803 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2803
dev_langs:
- C++
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51cf2a8b38a86fcd97ab693b3853fe25527a0bb3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236224"
---
# <a name="compiler-error-c2803"></a>コンパイラ エラー C2803
'operator 演算子' がクラス型の仮パラメーターを 1 つ以上あります。  
  
 オーバー ロードされた演算子には、クラス型のパラメーターが不足しています。  
  
 参照 (参照が、ポインターを使用していない) またはによって書き込むことができる値には、少なくとも 1 つのパラメーターを渡す必要がある"、< b"(の type クラス A と b)。  
  
 両方のパラメーターがポインターの場合はポインター アドレスの純粋な比較では、ユーザー定義の変換を使用しません。  
  
 次の例では、C2803 が生成されます。  
  
```  
// C2803.cpp  
// compile with: /c  
class A{};  
bool operator< (const A *left, const A *right);   // C2803  
// try the following line instead  
// bool operator< (const A& left, const A& right);  
```