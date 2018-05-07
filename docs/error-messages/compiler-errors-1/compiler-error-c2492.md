---
title: コンパイラ エラー C2492 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2492
dev_langs:
- C++
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68b3d769c5b86be172a0a27828fb1dc3905959d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2492"></a>コンパイラ エラー C2492
'*変数*': スレッド ストレージ存続期間を使用してデータには、dll インターフェイスはありません。    
  
 変数が宣言された、[スレッド](../../cpp/thread.md)属性し、DLL とインターフェイスします。 アドレス、`thread`変数が不明、実行時までため、DLL のインポートまたはエクスポートにリンクすることはできません。  
  
 次の例では、C2492 が生成されます。  
  
```  
// C2492.cpp  
// compile with: /c  
class C {  
public:  
   char   ch;  
};  
  
__declspec(dllexport) __declspec(thread) C c_1;   // C2492  
__declspec(thread) C c_1;   // OK  
```