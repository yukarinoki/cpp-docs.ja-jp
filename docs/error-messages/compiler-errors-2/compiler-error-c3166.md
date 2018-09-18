---
title: コンパイラ エラー C3166 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3166
dev_langs:
- C++
helpviewer_keywords:
- C3166
ms.assetid: ec3e330d-c15d-4158-8268-09101486c566
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c568f1732a4be5d890a5a654b09638828385383
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035514"
---
# <a name="compiler-error-c3166"></a>コンパイラ エラー C3166

'pointer': 'type' のメンバーとして、内部 _ _gc ポインターへのポインターを宣言することはできません

コンパイラは、無効なポインター宣言を検出 (、`__nogc`へのポインターを`__gc`ポインターです。)。

C3166 は古い形式のコンパイラ オプションを使用して到達のみ **/clr:oldSyntax**します。
