---
title: コンパイラ エラー C2466 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2466
dev_langs:
- C++
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e55e5c130b0a0454577a7155b704a18933b86198
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2466"></a>コンパイラ エラー C2466
サイズが 0 の配列を割り当てることができません。  
  
 配列が割り当てられているか、サイズが 0 で宣言されています。 配列のサイズの定数式は、0 より大きい整数である必要があります。 添字が 0 の配列宣言はクラス、構造体、または共用体メンバーに対してのみ、Microsoft 拡張機能でのみ有効です。 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md))。  
  
 次の例では、C2466 が生成されます。  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```