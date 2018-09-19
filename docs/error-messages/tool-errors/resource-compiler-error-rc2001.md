---
title: リソース コンパイラ エラー RC2001 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2001
dev_langs:
- C++
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d75d0f906ba0d7be75ca5177bc1f58bccd226251
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039973"
---
# <a name="resource-compiler-error-rc2001"></a>リソース コンパイラ エラー RC2001

定数の新しい行

文字列定数は続行されたことがなく行目では、円記号 (**\\**) または二重引用符をオープン/クローズ (**"**)。

ソース ファイル内の 2 つの行にある文字列定数を解除するには、次のいずれかの操作を行います。

- 行連結文字の円記号で最初の行を終了します。

- 二重引用符では、最初の行の文字列を閉じて、もう 1 つの引用符、次の行の文字列を開きます。

\N、文字列定数に改行文字を埋め込むためのエスケープ シーケンスでは、最初の行を終了するのに十分ではありません。