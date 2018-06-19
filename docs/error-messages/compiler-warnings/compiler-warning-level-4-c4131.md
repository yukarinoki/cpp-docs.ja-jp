---
title: コンパイラの警告 (レベル 4) C4131 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4131
dev_langs:
- C++
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6563d5faf3a9f050deb3cb7831c1a908739c8532
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291991"
---
# <a name="compiler-warning-level-4-c4131"></a>コンパイラの警告 (レベル 4) C4131
'function': 旧スタイルの宣言が使われています  
  
 指定された関数の宣言は、プロトタイプ形式ではありません。  
  
 旧スタイルの関数の宣言をプロトタイプ形式に変換する必要があります。  
  
 旧スタイルの関数の宣言の例を次に示します。  
  
```  
// C4131.c  
// compile with: /W4 /c  
void addrec( name, id ) // C4131 expected  
char *name;  
int id;  
{ }  
```  
  
 プロトタイプ形式の例を次に示します。  
  
```  
void addrec( char *name, int id )  
{ }  
```