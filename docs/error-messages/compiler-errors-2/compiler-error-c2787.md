---
title: コンパイラ エラー C2787 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2787
dev_langs:
- C++
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6b45d27c295b37d859d6451281f52c166dc1691
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2787"></a>コンパイラ エラー C2787
'identifier': このオブジェクトに関連付けられた GUID はありません。  
  
 [_ _Uuidof](../../cpp/uuidof-operator.md)操作はアタッチされている GUID またはユーザー定義型のオブジェクトで、ユーザー定義型を使用します。 このエラーは、引数が GUID を持つユーザー定義型である場合に発生しません。  
  
 次の例では、C2787 が生成されます。  
  
```  
// C2787.cpp  
#include <windows.h>  
struct F {};  
  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;  
  
int main() {  
   __uuidof(F);   // C2787  
   __uuidof(F2);   // OK  
}  
```