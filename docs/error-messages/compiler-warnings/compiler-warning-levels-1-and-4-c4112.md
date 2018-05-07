---
title: コンパイラの警告 (レベル 1 および 4) C4112 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4112
dev_langs:
- C++
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43718511af0d85f0c9026fe70b4749c4e3d4b1e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>コンパイラの警告 (レベル 1 および 4) C4112
\#行 1 と番号の間の整数が必要です。  
  
 許可された範囲を超えた整数パラメーターが [#line](../../preprocessor/hash-line-directive-c-cpp.md) ディレクティブに指定されています。  
  
 指定したパラメーターが 1 より小さい場合、行カウンターは 1 にリセットされます。 指定したパラメーターが、コンパイラで定義された制限値である *number*より大きい場合、行カウンターは変更されません。 これは、ANSI 互換オプション ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ではレベル 1 の警告であり、Microsoft 拡張機能オプション ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)) ではレベル 4 の警告です。  
  
 次の例では C4112 が生成されます。  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```