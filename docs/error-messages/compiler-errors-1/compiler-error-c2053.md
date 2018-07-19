---
title: コンパイラ エラー C2053 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2053
dev_langs:
- C++
helpviewer_keywords:
- C2053
ms.assetid: 13324c85-13a8-4996-bd42-a31bfe7ff80f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ace887e096ca0761f08843a033dc6391cb26aa99
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165296"
---
# <a name="compiler-error-c2053"></a>コンパイラ エラー C2053
'identifier': ワイド文字列が一致しません  
  
 ワイド文字列は、互換性のない型に割り当てられます。  
  
 次の例では、C2053 が生成されます。  
  
```  
// C2053.c  
int main() {  
   char array[] = L"Rika";   // C2053  
}  
```