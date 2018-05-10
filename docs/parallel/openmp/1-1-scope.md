---
title: 1.1 スコープ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48d14ec722299a9ff72ad5bab0a68cde5e00d6ad
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="11-scope"></a>1.1 スコープ
この仕様では、ユーザーが明示的に並列でプログラムを実行するために、コンパイラとランタイム システムで実行されるアクションを指定、のみのユーザー向けの並列について説明します。 OpenMP C および C++ の実装は、依存関係、競合、デッドロック、競合状態、または正しくないプログラムの実行と、その他の問題を確認する必要はありません。 ユーザーは、OpenMP C および C++ API コンストラクトを使用して、アプリケーションが正しく実行されることを保証します。 コンパイラによって生成された自動並列化し、このような並列処理を支援するために、コンパイラ ディレクティブは、このドキュメントでは説明しません。