---
title: リンカ ツール エラー LNK2008 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2008
dev_langs:
- C++
helpviewer_keywords:
- LNK2008
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18eda06e7f133ada4de1b7ec28ac21be205a71f7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086812"
---
# <a name="linker-tools-error-lnk2008"></a>リンカ ツール エラー LNK2008

Fixup ターゲットは、アラインされた 'symbol_name' ではありません。

リンクでは、配置が正しくがないオブジェクト ファイルの fixup ターゲットが見つかりません。

このエラーは、カスタム セクション配置によって発生することができます (たとえば、#pragma[パック](../../preprocessor/pack.md))、 [align](../../cpp/align-cpp.md)修飾子は、またはセクション配置を変更するアセンブリ言語コードを使用しています。

コードが、上記のいずれにも使わない場合はこれ、コンパイラによって発生する可能性があります。