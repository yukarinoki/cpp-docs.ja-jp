---
title: コンパイラ エラー C2692 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2692
dev_langs:
- C++
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03a9006889c5853e77b5603484ea9d18f2474241
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088372"
---
# <a name="compiler-error-c2692"></a>コンパイラ エラー C2692

'function_name': 完全なプロトタイプ関数が C コンパイラで必要な '/clr' オプション

マネージ コードを .NET のコンパイル時に、C コンパイラには、ANSI 関数の宣言が必要です。 さらに、関数がパラメーターを受け取らない場合は、する必要がありますを明示的に宣言`void`パラメーターの種類。