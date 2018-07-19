---
title: コンパイラ エラー C2341 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2341
dev_langs:
- C++
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18cc222129f3f12b5e7b5c6cb66e090907ff42a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197378"
---
# <a name="compiler-error-c2341"></a>コンパイラ エラー C2341
'section name': を使用するには、#pragma data_seg、code_seg または前のセクションを使用してセグメントを定義する必要があります  
  
 [割り当てる](../../cpp/allocate.md)ステートメントによって定義されていないセグメントを参照して[code_seg](../../preprocessor/code-seg.md)、 [data_seg](../../preprocessor/data-seg.md)、または[セクション](../../preprocessor/section.md)プラグマ。  
  
 次の例では、C2341 が生成されます。  
  
```  
// C2341.cpp  
// compile with: /c  
__declspec(allocate(".test"))   // C2341  
int j = 1;  
```  
  
 考えられる解決方法:  
  
```  
// C2341b.cpp  
// compile with: /c  
#pragma data_seg(".test")  
__declspec(allocate(".test"))  
int j = 1;  
```