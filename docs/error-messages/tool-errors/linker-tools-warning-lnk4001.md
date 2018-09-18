---
title: リンカー ツールの警告 LNK4001 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4001
dev_langs:
- C++
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f684e85233c4df777a53f03f07936137c425946e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070420"
---
# <a name="linker-tools-warning-lnk4001"></a>リンカー ツールの警告 LNK4001

オブジェクト ファイルが指定されていません。ライブラリを使用します

リンカーは、.obj ファイルは、1 つまたは複数の .lib ファイルに渡されました。

リンカーは、.obj ファイルにアクセスすることは、.lib ファイル内の情報にアクセスできないため、この警告は、その他のリンカー オプションを明示的に指定する必要があるを示します。 たとえばを指定する必要があります、 [/機械](../../build/reference/machine-specify-target-platform.md)、 [/out](../../build/reference/out-output-file-name.md)、または[/ENTRY](../../build/reference/entry-entry-point-symbol.md)オプション。