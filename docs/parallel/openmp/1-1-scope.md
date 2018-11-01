---
title: 1.1 スコープ
ms.date: 11/04/2016
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
ms.openlocfilehash: f87f631ae2d36662daa2ece4790170c00c5cbeb3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449206"
---
# <a name="11-scope"></a>1.1 スコープ

この仕様では、ユーザーが明示的に並列プログラムを実行するには、コンパイラとランタイム システムで実行するアクションを指定して、のみのユーザー向けの並列について説明します。 OpenMP C および C++ の実装は、依存関係、競合、デッドロック、競合状態、または正しくないプログラムの実行と、その他の問題を確認する必要はありません。 ユーザーは、OpenMP C および C++ API コンストラクトを使用して、アプリケーションが正しく実行されることを保証します。 コンパイラによって生成された自動並列化し、このような並列処理を支援するために、コンパイラ ディレクティブは、このドキュメントでは説明しません。