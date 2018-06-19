---
title: コンパイラの警告 (レベル 3) C4159 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4159
dev_langs:
- C++
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 139a21f5fbb7ce279d96f9df8be6008c2f092287
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291672"
---
# <a name="compiler-warning-level-3-c4159"></a>コンパイラの警告 (レベル 3) C4159
\#プラグマ pragma(pop,...): 以前にプッシュされた識別子 'identifier' がポップされます。  
  
 ソース コードに含まれる、**プッシュ**、プラグマの識別子の命令が続く、 **pop**識別子なし命令します。 その結果、***識別子***の表示された、およびそれ以降の使用は、***識別子***予期しない動作が発生する可能性があります。  
  
 この警告を回避するで識別子を指定、 **pop**命令します。 例えば:  
  
```  
// C4159.cpp  
// compile with: /W3  
#pragma pack(push, f)  
#pragma pack(pop)   // C4159  
  
// using the identifier resolves the warning  
// #pragma pack(pop, f)  
  
int main()  
{  
}  
```