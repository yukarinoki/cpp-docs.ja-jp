---
title: コンパイラの警告 (レベル 1) C4124 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4124
dev_langs:
- C++
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: accd58c123bcd74e54176eed5eb974c3df33dbab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4124"></a>コンパイラの警告 (レベル 1) C4124
_ _fastcall スタック チェックでは効率的ではありません。  
  
 `__fastcall`スタック チェックが有効でキーワードが使用されました。  
  
 `__fastcall`規則には、高速のコードが生成されますが、低速コードをスタック チェックします。 使用する場合`__fastcall`、スタック チェックをオフにする、 **check_stack**プラグマまたは/Gs です。  
  
 この警告は、最初にこれらの条件下で宣言された関数に対してのみ実行されます。