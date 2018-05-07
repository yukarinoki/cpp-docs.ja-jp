---
title: 致命的なエラー C1005 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1005
dev_langs:
- C++
helpviewer_keywords:
- C1005
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13ff7f5dbc1f9ecb66c54f52fae4a38d1e4d4664
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1005"></a>致命的なエラー C1005
コンパイラの中間ファイルの文字列がバッファーの大きさを超えました。  
  
 コンパイラの中間ファイル内の文字列で、バッファーがオーバーフローしました。  
  
 このエラーは、 [/Fd](../../build/reference/fd-program-database-file-name.md) または [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) コンパイラ オプションに渡すパラメーターが 256 バイトを超えている場合に発生することがあります。