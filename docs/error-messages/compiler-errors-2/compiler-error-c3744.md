---
description: 詳細については、「コンパイラエラー C3744」を参照してください。
title: コンパイラ エラー C3744
ms.date: 11/04/2016
f1_keywords:
- C3744
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
ms.openlocfilehash: 6d8e9184db37f65fd73a85aaaa6c350303802216
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340230"
---
# <a name="compiler-error-c3744"></a>コンパイラ エラー C3744

__unhook には、マネージイベントに対して少なくとも3つの引数が必要です

[`__unhook`](../../cpp/unhook.md)Managed Extensions for C++ 用にコンパイルされたプログラムで使用する場合、関数は3つのパラメーターを受け取る必要があります。

**`__hook`** および **`__unhook`** は、プログラミングと互換性がありません **`/clr`** 。 代わりに、+ = 演算子と-= 演算子を使用します。

C3744 は、互換性のために残されているコンパイラオプションを使用してのみ到達可能です **`/clr:oldSyntax`** 。
