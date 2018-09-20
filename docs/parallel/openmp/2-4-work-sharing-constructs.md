---
title: 2.4 動作共有のコンストラクト |Microsoft Docs
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
ms.openlocfilehash: 719b33698b708761f0cd56e65a70a6ea8fa3b053
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411119"
---
# <a name="24-work-sharing-constructs"></a>2.4 動作共有のコンストラクト

Work-sharing コンス トラクターは、これを検出したチームのメンバーの間で関連付けられているステートメントの実行を配布します。 動作共有ディレクティブは、新しいスレッドを起動しないと、エントリ work-sharing コンス トラクターを暗黙の壁がなくなります。

作業の共有のシーケンスを構築し、**バリア**で発生するディレクティブは、チーム内のすべてのスレッドで同じである必要があります。

OpenMP は、次動作共有のコンストラクトを定義し、これらは、次のセクションで説明されています。

- **ディ**レクティブ

- **セクション**ディレクティブ

- **1 つ**ディレクティブ