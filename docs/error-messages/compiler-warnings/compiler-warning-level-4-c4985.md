---
description: '詳細情報: コンパイラの警告 (レベル 4) C4985'
title: コンパイラの警告 (レベル 4) C4985
ms.date: 11/04/2016
f1_keywords:
- C4985
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
ms.openlocfilehash: c00c6ebd16f5160ffed726eae5307d7f3642eb3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234567"
---
# <a name="compiler-warning-level-4-c4985"></a>コンパイラの警告 (レベル 4) C4985

> '*symbol name*': 前の宣言に属性が存在しません。

現在のメソッドの宣言または定義の Microsoft ソース コード注釈言語 (SAL) の注釈が、前の宣言の注釈と異なります。 メソッドの定義と宣言では同じ SAL 注釈を使用する必要があります。

SAL はユーザーが使用できる注釈のセットを提供して、関数が自身のパラメーターをどのように使用するかを記述します。つまり、これらの注釈は、関数がそのパラメーターについて何を前提としているか、関数が終了時に何を保証するかを示します。 注釈は sal.h ヘッダー ファイルで定義されています。

プロジェクトにフラグが指定されていないと、SAL マクロは展開されません [`/analyze`](../../build/reference/analyze-code-analysis.md) 。 を指定すると **`/analyze`** 、警告やエラーが発生しない場合でも、コンパイラは C4985 をスローでき **`/analyze`** ます。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. メソッドの定義と、そのすべての宣言で、同じ SAL 注釈を使用します。

## <a name="see-also"></a>関連項目

[SAL 注釈](../../c-runtime-library/sal-annotations.md)
