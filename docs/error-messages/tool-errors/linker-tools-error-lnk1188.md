---
title: リンカ ツール エラー LNK1188 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1188
dev_langs:
- C++
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e31943ae253a332576fba73102db410b103a0096
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1188"></a>リンカ ツール エラー LNK1188
BADFIXUPSECTION:: 無効な fixup ターゲット 'symbol';考えられる長さのセクションは 0  
  
 VxD リンク中に再配置のターゲットは、セクションがありませんでした。 Link386 (以前のバージョン)、(MASM GROUP ディレクティブによって生成された) OMF グループ レコードが 0 長セクションには、長さが 0 以外の別のセクションを結合に使用されている可能性があります。 COFF 形式は、長さゼロのセクションでは、GROUP ディレクティブをサポートしていません。 リンクでは、この種類の OMF オブジェクトが COFF に自動的に変換、このエラーが発生する可能性があります。