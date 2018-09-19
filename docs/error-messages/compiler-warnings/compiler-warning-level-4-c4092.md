---
title: コンパイラの警告 (レベル 4) C4092 |Microsoft Docs
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
ms.openlocfilehash: 84aa73120dabd261d54e764d1e0bfe8bc9c561a0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039615"
---
# <a name="compiler-warning-level-4-c4092"></a>コンパイラの警告 (レベル 4) C4092

sizeof 演算子が 'unsigned long'。

オペランド、`sizeof`演算子が非常に多いため、`sizeof`符号なしで返される**長い**します。 Microsoft 拡張機能でこの警告が発生します ([/Ze](../../build/reference/za-ze-disable-language-extensions.md))。 ANSI 互換 (/Za) では、代わりに、結果が切り捨てられます。