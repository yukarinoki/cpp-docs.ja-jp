---
title: リンカ ツール エラー LNK2008 |Microsoft ドキュメント
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
ms.openlocfilehash: c4ee6a8a4c4cc6d33f47d5335daa9fccd4e5fd99
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299566"
---
# <a name="linker-tools-error-lnk2008"></a>リンカ ツール エラー LNK2008
Fixup ターゲットは、アラインされた 'symbol_name' ではありません。  
  
 リンクは、配置が正しくがないをオブジェクト ファイルに fixup ターゲットを検出します。  
  
 このエラーは、カスタムのセクション配置によって発生することができます (たとえば、#pragma[パック](../../preprocessor/pack.md))、[整列](../../cpp/align-cpp.md)修飾子は、またはセクション配置を変更するアセンブリ言語のコードを使用しています。  
  
 コードは使用しない場合、上記のいずれか、コンパイラこれによる可能性があります。