---
title: コンパイラ エラー C2856
ms.date: 11/04/2016
f1_keywords:
- C2856
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
ms.openlocfilehash: 1e515f250c8ab9d1008ded91b99176f1d86d7cd1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499607"
---
# <a name="compiler-error-c2856"></a>コンパイラ エラー C2856

\#プラグマ hdrstop は #if ブロックの内部ですることはできません。

`hdrstop`プラグマは、条件付きコンパイル ブロックの本文内に配置することはできません。

移動、`#pragma hdrstop`ステートメントに含まれていない領域に、`#if/#endif`ブロックします。