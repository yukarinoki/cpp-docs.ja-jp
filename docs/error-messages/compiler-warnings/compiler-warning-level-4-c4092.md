---
title: コンパイラの警告 (レベル 4) C4092 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4092
dev_langs:
- C++
helpviewer_keywords:
- C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ca145addc16306d613817643e363ecd9c95069a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292189"
---
# <a name="compiler-warning-level-4-c4092"></a>コンパイラの警告 (レベル 4) C4092
sizeof 演算子 'unsigned long'。  
  
 オペランド、`sizeof`演算子が非常に多いため、`sizeof`符号なしで返される**長い**です。 この警告は、Microsoft 拡張機能 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md))。 ANSI 互換 (/Za)、代わりに、結果が切り捨てられます。