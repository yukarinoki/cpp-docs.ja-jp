---
title: リンカー ツールの警告 LNK4001 |Microsoft ドキュメント
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
ms.openlocfilehash: acf65c00c5c039769a05e009dcfe46ea42633ac4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4001"></a>リンカー ツールの警告 LNK4001
オブジェクト ファイルが指定されていません。ライブラリを使用します  
  
 リンカーが渡されましたが、1 つまたは複数の .lib ファイル、.obj ファイルがありません。  
  
 リンカーは、.obj ファイルにアクセスすることである .lib ファイル内の情報にアクセスできないために、この警告は、その他のリンカー オプションを明示的に指定する必要があるを示します。 たとえばを指定する必要があります、[マシン/](../../build/reference/machine-specify-target-platform.md)、 [/out](../../build/reference/out-output-file-name.md)、または[/ENTRY](../../build/reference/entry-entry-point-symbol.md)オプション。