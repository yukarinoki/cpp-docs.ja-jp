---
title: コンパイラ エラー C2218 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2218
dev_langs:
- C++
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1efda7258616862efc464b493b51ada2c6bd7674
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2218"></a>コンパイラ エラー C2218
'__vectorcall' と '/arch:IA32' は同時に使用できません  
  
 `__vectorcall` の呼び出し規約は、SSE2 (Streaming SIMD Extensions 2) 以上が搭載された x86 および x64 プロセッサのネイティブ コードでのみサポートされます。 詳細については、次を参照してください。 [_ _vectorcall](../../cpp/vectorcall.md)です。  
  
 このエラーを修正するには、SSE2、AVX、または AVX2 をターゲットにするようにコンパイラ オプションを変更します。 詳細については、「[/arch (x86)](../../build/reference/arch-x86.md)」を参照してください。