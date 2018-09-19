---
title: コンパイラの警告 (レベル 1) C4650 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4650
dev_langs:
- C++
helpviewer_keywords:
- C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d49b21452465f26d6e696f928c04c20dc0e33307
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052897"
---
# <a name="compiler-warning-level-1-c4650"></a>コンパイラの警告 (レベル 1) C4650

プリコンパイル済みヘッダー以外ではなくデバッグ情報ヘッダーからのグローバル シンボルのみが提供されます。

プリコンパイル済みヘッダー ファイルは、シンボリック デバッグ情報の Microsoft ではコンパイルされませんでした。

リンクされるとき、生成された実行可能ファイルまたはダイナミック リンク ライブラリ ファイルには、プリコンパイル済みヘッダーに含まれるローカル シンボルのデバッグ情報は含まれません。

プリコンパイル済みヘッダー ファイルを再コンパイルでは、この警告を回避できます、 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)コマンド ライン オプション。