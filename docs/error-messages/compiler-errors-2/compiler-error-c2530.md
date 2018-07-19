---
title: コンパイラ エラー C2530 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2530
dev_langs:
- C++
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b226ef5ca0e839c745e13d4118264a69ca408db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229403"
---
# <a name="compiler-error-c2530"></a>コンパイラ エラー C2530
'identifier': 参照を初期化する必要があります  
  
 既に宣言されていない限り、宣言されているときに参照を初期化する必要があります。  
  
-   キーワードを使用して[extern](../../cpp/using-extern-to-specify-linkage.md)です。  
  
-   クラス、構造体、または共用体のメンバーとして (および、コンス トラクターで初期化されます)。  
  
-   関数宣言または定義でパラメーター。  
  
-   関数の戻り値の型。  
  
 次の例では、C2530 が生成されます。  
  
```  
// C2530.cpp  
int main() {  
   int i = 0;  
   int &j;   // C2530  
   int &k = i;   // OK  
}  
```