---
title: 2.4 動作共有のコンストラクト
ms.date: 11/04/2016
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
ms.openlocfilehash: e7bf8d37ecdc6a3ef451c9d9746fb47a76a16eb4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502883"
---
# <a name="24-work-sharing-constructs"></a>2.4 動作共有のコンストラクト

Work-sharing コンス トラクターは、これを検出したチームのメンバーの間で関連付けられているステートメントの実行を配布します。 動作共有ディレクティブは、新しいスレッドを起動しないと、エントリ work-sharing コンス トラクターを暗黙の壁がなくなります。

作業の共有のシーケンスを構築し、**バリア**で発生するディレクティブは、チーム内のすべてのスレッドで同じである必要があります。

OpenMP は、次動作共有のコンストラクトを定義し、これらは、次のセクションで説明されています。

- **ディ**レクティブ

- **セクション**ディレクティブ

- **1 つ**ディレクティブ