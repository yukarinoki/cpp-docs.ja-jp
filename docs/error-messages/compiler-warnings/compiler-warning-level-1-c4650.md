---
title: コンパイラの警告 (レベル 1) C4650 |Microsoft ドキュメント
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
ms.openlocfilehash: 6cb1c9979141e7958b6c2802aaf321efe41e9570
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283086"
---
# <a name="compiler-warning-level-1-c4650"></a>コンパイラの警告 (レベル 1) C4650
プリコンパイル済みヘッダー以外ではなく、デバッグ情報ヘッダーからのグローバル シンボルのみが使用できます。  
  
 プリコンパイル済みヘッダー ファイルは、Microsoft シンボリック デバッグ情報にコンパイルされませんでした。  
  
 リンクしているときに生成された実行可能ファイルまたはダイナミック リンク ライブラリ ファイルには、プリコンパイル済みヘッダーに含まれているローカル シンボルのデバッグ情報は含まれません。  
  
 この警告を回避でプリコンパイル済みヘッダー ファイルを再コンパイルを[/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)コマンド ライン オプションです。