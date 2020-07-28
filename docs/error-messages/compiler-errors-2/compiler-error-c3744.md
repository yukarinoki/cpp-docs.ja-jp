---
title: コンパイラ エラー C3744
ms.date: 11/04/2016
f1_keywords:
- C3744
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
ms.openlocfilehash: 8db81afc348434e9ea2f57c991962fb15dc6bf98
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220159"
---
# <a name="compiler-error-c3744"></a>コンパイラ エラー C3744

__unhook には、マネージイベントに対して少なくとも3つの引数が必要です

[`__unhook`](../../cpp/unhook.md)Managed Extensions for C++ 用にコンパイルされたプログラムで使用する場合、関数は3つのパラメーターを受け取る必要があります。

**`__hook`** および **`__unhook`** は、プログラミングと互換性がありません **`/clr`** 。 代わりに、+ = 演算子と-= 演算子を使用します。

C3744 は、互換性のために残されているコンパイラオプションを使用してのみ到達可能です **`/clr:oldSyntax`** 。
