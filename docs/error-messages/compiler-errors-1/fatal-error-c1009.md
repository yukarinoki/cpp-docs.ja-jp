---
title: 致命的なエラー C1009 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1009
dev_langs:
- C++
helpviewer_keywords:
- C1009
ms.assetid: dcc8383c-3362-4c47-9c26-25d2451ebd53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 665d868aeacbaf5c62bf59a4400baa2b31569972
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198730"
---
# <a name="fatal-error-c1009"></a>致命的なエラー C1009
コンパイラの制限: マクロの入れ子のレベルが深すぎます  
  
 コンパイラは、同時に多数のマクロを展開しようとしました。 コンパイラは、マクロの入れ子レベルは、256 に制限します。 入れ子になったマクロを簡単なマクロに分割します。