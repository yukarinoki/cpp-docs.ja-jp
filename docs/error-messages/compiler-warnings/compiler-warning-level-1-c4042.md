---
title: コンパイラの警告 (レベル 1) C4042 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4042
dev_langs:
- C++
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcc4123c18eb9765841a5f6b54446cd064407700
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278386"
---
# <a name="compiler-warning-level-1-c4042"></a>コンパイラの警告 (レベル 1) C4042
'identifier': 無効なストレージ クラスがあります。  
  
 指定されたストレージ クラスは、このコンテキストでこの識別子に使用できません。 コンパイラは、代わりに既定のストレージ クラスを使用します。  
  
-   `extern`、場合*識別子*関数です。  
  
-   **自動**場合は、*識別子*仮パラメーターまたはローカル変数です。  
  
-   ストレージ クラスのない場合、*識別子*グローバル変数です。  
  
 この警告は、ストレージ クラスを以外の値を指定することによって発生**登録**パラメーターの宣言でします。  
  
 次の例には、C4042 が生成されます。  
  
```  
// C4042.cpp  
// compile with: /W1 /LD  
int func2( __declspec( thread ) int tls_i )    // C4042  
// try the following line instead  
// int func2( int tls_i )  
{  
   return tls_i;  
}  
```