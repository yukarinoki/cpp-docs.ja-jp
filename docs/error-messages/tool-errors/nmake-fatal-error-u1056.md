---
title: NMAKE の致命的なエラー U1056 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1056
dev_langs:
- C++
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0a83c62bedf995708d5e99fee19f05696d05c2d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065700"
---
# <a name="nmake-fatal-error-u1056"></a>NMAKE の致命的なエラー U1056

コマンド プロセッサを見つけることができません。

指定されたパスでコマンド プロセッサはなかった、 **COMSPEC**または**パス**環境変数。

NMAKE は COMMAND.COM または cmd.コマンドを実行するときに、コマンド プロセッサとして実行します。 検索コマンド プロセッサを最初設定されているパス**COMSPEC**します。 場合**COMSPEC** (nmake の) の検索で指定されたディレクトリが存在しない**パス**します。