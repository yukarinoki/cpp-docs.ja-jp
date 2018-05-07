---
title: コンパイラの警告 (レベル 4) C4032 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4032
dev_langs:
- C++
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb61588c12378972194305d979ecdd89140ac6f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4032"></a>コンパイラの警告 (レベル 4) C4032
仮パラメーター 'number' が昇格するときに別の種類  
  
 パラメーターの型が互換性のある、既定値のプロモーション、前の宣言で型を使用できません。  
  
 これは ANSI C ではエラー ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) と Microsoft 拡張機能 (/Ze) では警告です。  
  
## <a name="example"></a>例  
  
```  
// C4032.c  
// compile with: /W4  
void func();  
void func(char);   // C4032, char promotes to int  
  
int main()  
{  
}  
```