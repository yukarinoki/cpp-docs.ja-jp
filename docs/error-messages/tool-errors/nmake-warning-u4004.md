---
title: NMAKE の警告 U4004 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4004
dev_langs:
- C++
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 532abf2f62616d6e748c9a4e34f5c983f0853276
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317181"
---
# <a name="nmake-warning-u4004"></a>NMAKE の警告 U4004
ターゲット 'targetname' のルールが多すぎます  
  
 1 つ以上の記述ブロックでは、1 つのコロンを使用して指定されたターゲットが指定されました (**:**) 区切り記号として。 (Nmake の) は、最初の記述ブロックのコマンドを実行し、後のブロックを無視します。  
  
 同じターゲットを複数の依存関係を指定するには、2 つのコロンを使用して (`::`) で各依存関係行区切り記号として。