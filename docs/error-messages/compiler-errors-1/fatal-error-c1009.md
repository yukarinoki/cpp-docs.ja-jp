---
title: 致命的なエラー C1009 |Microsoft Docs
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
ms.openlocfilehash: b1fbd8994be6fd86a764db400d8761a5d697079b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037334"
---
# <a name="fatal-error-c1009"></a>致命的なエラー C1009

コンパイラの制限: マクロの入れ子のレベルが深すぎます

コンパイラが同時にマクロが多すぎますを展開しようとするとします。 コンパイラでは、マクロの入れ子レベルの 256 の制限があります。 入れ子になったマクロを簡単なマクロに分割します。