---
title: コンパイラ エラー C2480 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2480
dev_langs:
- C++
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 987cefa42b3f3f8d9588e446ca181c0b7cd48f8c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198587"
---
# <a name="compiler-error-c2480"></a>コンパイラ エラー C2480
'identifier': 'thread' は静的なデータ項目の有効なのみ  
  
 使用することはできません、`thread`属性と自動変数、非静的データ メンバー、関数パラメーター、または関数宣言または定義します。  
  
 使用して、`thread`属性をグローバル変数、静的データ メンバー、およびローカルの静的変数のみです。  
  
 次の例では、C2480 が生成されます。  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```