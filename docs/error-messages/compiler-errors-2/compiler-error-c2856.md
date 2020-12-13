---
description: 詳細については、「コンパイラエラー C2856」を参照してください。
title: コンパイラ エラー C2856
ms.date: 11/04/2016
f1_keywords:
- C2856
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
ms.openlocfilehash: 8594bc5902e13967084aa3695131d616a4cf04da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337545"
---
# <a name="compiler-error-c2856"></a>コンパイラ エラー C2856

\#プラグマ hdrstop を #if ブロック内に指定することはできません

`hdrstop`プラグマを条件付きコンパイルブロックの本体内に配置することはできません。

ステートメントを `#pragma hdrstop` ブロックに含まれていない領域に移動 `#if/#endif` します。
