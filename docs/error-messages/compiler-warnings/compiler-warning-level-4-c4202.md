---
title: コンパイラの警告 (レベル 4) C4202 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4202
dev_langs:
- C++
helpviewer_keywords:
- C4202
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dea55835c75a0ac1d5646a542675eefa2c5e5254
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4202"></a>コンパイラの警告 (レベル 4) C4202
使用される標準の拡張機能: '…': プロトタイプのパラメーター名 ボックスの一覧が不正です。  
  
 旧スタイルの関数定義には、可変個の引数が含まれています。 これらの定義は、ANSI 互換のエラーを生成 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。  
  
## <a name="example"></a>例  
  
```  
// C4202.c  
// compile with: /W4  
void func( a, b, ...)   // C4202  
int a, b;  
{}  
  
int main()  
{  
}  
```