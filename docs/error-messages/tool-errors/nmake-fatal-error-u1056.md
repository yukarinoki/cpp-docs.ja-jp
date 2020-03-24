---
title: NMAKE の致命的なエラー U1056
ms.date: 11/04/2016
f1_keywords:
- U1056
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
ms.openlocfilehash: 10131e518fa608292fff58672ede36390bcd665b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182904"
---
# <a name="nmake-fatal-error-u1056"></a>NMAKE の致命的なエラー U1056

コマンドプロセッサが見つかりません

コマンドプロセッサが、 **COMSPEC**または**path**環境変数で指定されたパスにありませんでした。

NMAKE は、COMMAND.COM または CMD を使用します。コマンドを実行するときのコマンドプロセッサとしての実行可能ファイル。 **COMSPEC**で設定されているパスで、最初にコマンドプロセッサが検索されます。 **COMSPEC**が存在しない場合、NMAKE は**PATH**で指定されたディレクトリを検索します。
