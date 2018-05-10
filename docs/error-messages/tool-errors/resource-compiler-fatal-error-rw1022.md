---
title: リソース コンパイラの致命的なエラー RW1022 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW1022
dev_langs:
- C++
helpviewer_keywords:
- RW1022
ms.assetid: 6747c8a9-9c9b-4422-b414-0645d22092d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f57bb435d17cf1d539d558b5dead9c299f83494a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-fatal-error-rw1022"></a>リソース コンパイラの致命的なエラー RW1022
**ファイルの書き込み I/O エラー**  
  
 リソース コンパイラは、ファイルに書き込めませんでした。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  ディスク領域が不足しています。 空き領域を作成する実行可能ファイルのサイズの少なくとも 2 倍に等しくなければなりません。  
  
2.  ボリュームが読み取り専用です。  
  
3.  正しくないセクターです。  
  
4.  共有違反です。