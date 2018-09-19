---
title: コンパイラの警告 (レベル 1) C4124 |Microsoft Docs
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
ms.openlocfilehash: a69190487c22987ead2d00ec102785ed42ea93c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090933"
---
# <a name="compiler-warning-level-1-c4124"></a>コンパイラの警告 (レベル 1) C4124

_ _fastcall スタック チェックでは効率的ではありません。

`__fastcall`キーワードは、スタック チェックが有効で使用されました。

`__fastcall`規則には、高速のコードが生成されますが、低速コードをスタック チェックします。 使用する場合`__fastcall`、スタックのチェックをオフにする、 **check_stack**プラグマまたは/Gs します。

最初にこれらの条件下で宣言された関数にのみ警告が表示されます。