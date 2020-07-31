---
title: コンパイラエラー C3166
ms.date: 11/04/2016
f1_keywords:
- C3166
helpviewer_keywords:
- C3166
ms.assetid: ec3e330d-c15d-4158-8268-09101486c566
ms.openlocfilehash: 1915d58f73ce8d16135951b359c3f0fd48aea3ac
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230871"
---
# <a name="compiler-error-c3166"></a>コンパイラエラー C3166

> ' pointer ': 内部 __gc ポインターへのポインターを ' type ' のメンバーとして宣言することはできません

コンパイラは、無効なポインター宣言 (ポインター **`__nogc`** へのポインター) を検出しました **`__gc`** 。

C3166 は、互換性のために残されているコンパイラオプションを使用してのみ到達可能です **`/clr:oldSyntax`** 。
