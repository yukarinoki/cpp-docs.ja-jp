---
title: リンカー ツールの警告 LNK4071 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4071
dev_langs:
- C++
helpviewer_keywords:
- LNK4071
ms.assetid: 803f8c34-8219-4f55-a4ae-7133ceff2ba3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d11247c823a93604359b4cab6995b694bcf5a2f3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064677"
---
# <a name="linker-tools-warning-lnk4071"></a>リンカー ツールの警告 LNK4071

以降のリンクではインクリメンタル リンクすることはできません。

リンクが 1 つまたは複数のシンボルを複数の定義が見つかりましたが、 [/force](../../build/reference/force-force-file-output.md)または **/FORCE:MULTIPLE**エラーに関係なく、出力ファイルを作成するために使用されました。 リンクは、インクリメンタル ステータス (.ilk) ファイルを削除します。