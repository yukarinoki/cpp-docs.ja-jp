---
title: リンカ ツール エラー LNK1245 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1245
dev_langs:
- C++
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47a1c2e5f7bf66946dcc5816d7a20fd485b59b45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1245"></a>リンカ ツール エラー LNK1245
無効なサブシステム 'サブシステム' が指定されています。/SUBSYSTEM は、WINDOWS、WINDOWSCE、またはコンソールをする必要があります。  
  
 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)オブジェクトをコンパイルに使用された、次の条件のいずれかが true とします。  
  
-   カスタムのエントリ ポイントが定義されている ([/ENTRY](../../build/reference/entry-entry-point-symbol.md))、そのようなリンカーは、サブシステムを推論できませんでした。  
  
-   渡された値、 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)リンカー オプションは/clr オブジェクトに対して無効です。  
  
 どちらの場合は、解像度は、/SUBSYSTEM リンカー オプションを有効な値を指定します。