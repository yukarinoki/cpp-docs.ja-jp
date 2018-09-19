---
title: 数値演算エラー M6110 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6110
dev_langs:
- C++
helpviewer_keywords:
- M6110
ms.assetid: aac9ae37-6a6d-46e9-85d4-dfe03f1c3e11
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 333a6d9741d4ccaa5764e84fabd71f58788c1b6d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46015797"
---
# <a name="math-error-m6110"></a>数値演算エラー M6110

スタック オーバーフロー

浮動小数点式には、浮動小数点スタック オーバーフローが発生します。

浮動小数点例外のスタック オーバーフローは、8087/287/387 コプロセッサでサポートされる、通常、8 つのレベルだけでなく、7 つのレベルの上限に達するまでにトラップされます。

終了コード 138 でプログラムを終了します。