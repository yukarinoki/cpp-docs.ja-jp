---
title: コンパイラの警告 (レベル 1) C4799 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4799
dev_langs:
- C++
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f888d6a941ad487ce122e46c43582e1c96525c70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282939"
---
# <a name="compiler-warning-level-1-c4799"></a>コンパイラの警告 (レベル 1) C4799  
  
> 関数の最後にない EMM '*関数*'  
  
関数は、少なくとも 1 つの MMX 命令を持つ必要はありません、`EMMS`命令します。 マルチ メディアの命令を使用すると、`EMMS`命令または`_mm_empty`組み込みを使用することも MMX コードの最後に、マルチ メディア タグ単語をオフにします。  
  
返す前に EMMS 命令 ivec.h コードが正しく使用されないことを使用して実行すると、C4799 を表示可能性があります。 これは、これらのヘッダーの場合は false 警告です。 これら操作は、ivec.h で _SILENCE_IVEC_C4799 を定義することで無効に可能性があります。 ただし、これでも保持すること、コンパイラからこの型の正しい警告に注意してください。  
  
関連情報については、次を参照してください。 [Intel's MMX 命令セット](../../assembler/inline/intel-s-mmx-instruction-set.md)です。