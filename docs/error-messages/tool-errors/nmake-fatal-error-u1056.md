---
description: 詳細については、「NMAKE の致命的なエラー U1056」を参照してください。
title: NMAKE の致命的なエラー U1056
ms.date: 11/04/2016
f1_keywords:
- U1056
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
ms.openlocfilehash: beb7814d2e29665e1f92c7ef1e8dadbd66af5d63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330376"
---
# <a name="nmake-fatal-error-u1056"></a>NMAKE の致命的なエラー U1056

コマンドプロセッサが見つかりません

コマンドプロセッサが、 **COMSPEC** または **path** 環境変数で指定されたパスにありませんでした。

NMAKE では、コマンドの実行時にコマンドプロセッサとして COMMAND.COM または CMD.EXE を使用します。 **COMSPEC** で設定されているパスで、最初にコマンドプロセッサが検索されます。 **COMSPEC** が存在しない場合、NMAKE は **PATH** で指定されたディレクトリを検索します。
