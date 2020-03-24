---
title: コンパイラ エラー C2856
ms.date: 11/04/2016
f1_keywords:
- C2856
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
ms.openlocfilehash: c88610607083ecfaf5f20cd585b479991fa51b44
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201890"
---
# <a name="compiler-error-c2856"></a>コンパイラ エラー C2856

\#プラグマ hdrstop を #if ブロック内に指定することはできません

`hdrstop` プラグマを条件付きコンパイルブロックの本体内に配置することはできません。

`#pragma hdrstop` ステートメントを `#if/#endif` ブロックに含まれていない領域に移動します。
