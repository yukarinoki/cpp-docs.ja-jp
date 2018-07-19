---
title: コンパイラ エラー C2833 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2833
dev_langs:
- C++
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff066510292690bc940f18ab8d63605eb8627308
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33244111"
---
# <a name="compiler-error-c2833"></a>コンパイラ エラー C2833
'operator 演算子' は認識されている演算子または型ではありません。  
  
 単語`operator`をオーバーライドする演算子または変換する型が続かなければなりません。  
  
 マネージ型で定義できる演算子の一覧は、次を参照してください。[ユーザー定義の演算子](../../dotnet/user-defined-operators-cpp-cli.md)です。  
  
 次の例では、C2833 が生成されます。  
  
```  
// C2833.cpp  
// compile with: /c  
class A {};  
  
void operator ::* ();   // C2833  
void operator :: ();   // OK  
```