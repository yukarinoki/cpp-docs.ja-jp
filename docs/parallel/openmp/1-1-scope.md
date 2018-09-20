---
title: 1.1 スコープ |Microsoft Docs
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
ms.openlocfilehash: 81babf799860030f6d398f64b55ed65039de8649
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393532"
---
# <a name="11-scope"></a>1.1 スコープ

この仕様では、ユーザーが明示的に並列プログラムを実行するには、コンパイラとランタイム システムで実行するアクションを指定して、のみのユーザー向けの並列について説明します。 OpenMP C および C++ の実装は、依存関係、競合、デッドロック、競合状態、または正しくないプログラムの実行と、その他の問題を確認する必要はありません。 ユーザーは、OpenMP C および C++ API コンストラクトを使用して、アプリケーションが正しく実行されることを保証します。 コンパイラによって生成された自動並列化し、このような並列処理を支援するために、コンパイラ ディレクティブは、このドキュメントでは説明しません。