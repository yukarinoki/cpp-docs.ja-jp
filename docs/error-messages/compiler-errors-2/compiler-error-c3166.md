---
description: 詳細については、「コンパイラエラー C3166」を参照してください。
title: コンパイラエラー C3166
ms.date: 11/04/2016
f1_keywords:
- C3166
helpviewer_keywords:
- C3166
ms.assetid: ec3e330d-c15d-4158-8268-09101486c566
ms.openlocfilehash: c92883fec3fd68b969a6d357f8c3fab2f5a3aea1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242289"
---
# <a name="compiler-error-c3166"></a>コンパイラエラー C3166

> ' pointer ': 内部 __gc ポインターへのポインターを ' type ' のメンバーとして宣言することはできません

コンパイラは、無効なポインター宣言 (ポインター **`__nogc`** へのポインター) を検出しました **`__gc`** 。

C3166 は、互換性のために残されているコンパイラオプションを使用してのみ到達可能です **`/clr:oldSyntax`** 。
