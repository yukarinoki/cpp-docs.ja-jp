---
title: 2.4 動作共有のコンストラクト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c00eb94055f26954a283a6172f69228804832ac4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="24-work-sharing-constructs"></a>2.4 動作共有のコンストラクト
Work-sharing コンス トラクターは、これを検出した、チームのメンバーのうち、関連するステートメントの実行を配布します。 動作共有ディレクティブでは、新しいスレッドが起動しないと、work-sharing コンス トラクターへのエントリに暗黙のバリアはありません。  
  
 動作共有のシーケンスの構築と**バリア**で発生するディレクティブは、チームの各スレッドで同じである必要があります。  
  
 OpenMP には、次の work-sharing コンス トラクターを定義し、これらは後に続くセクションで説明。  
  
-   **デ**ィレクティブ  
  
-   **セクションでは**ディレクティブ  
  
-   **1 つ**ディレクティブ