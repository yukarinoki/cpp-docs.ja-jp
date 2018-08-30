---
title: コンパイラの警告 (レベル 3) C4306 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4306
dev_langs:
- C++
helpviewer_keywords:
- C4306
ms.assetid: 5b2192d7-402d-4b6d-8619-08105e7dcac7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab5372213819375a6c1fec3cfc43970415b6486a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219995"
---
# <a name="compiler-warning-level-3-c4306"></a>コンパイラの警告 (レベル 3) C4306

> '*識別子*': から変換'*type1*'to'*type2*' より大きいサイズの

識別子の型は、大きいサイズのポインターにキャストします。 新しい種類の塗りつぶされていない上位ビットはゼロで埋められますになります。

この警告は、不要な変換である可能性があります。 結果のポインターは有効でない可能性があります。