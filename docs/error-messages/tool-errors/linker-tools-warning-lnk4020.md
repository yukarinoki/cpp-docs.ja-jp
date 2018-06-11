---
title: リンカー ツールの警告 LNK4020 |Microsoft ドキュメント
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4020
dev_langs:
- C++
helpviewer_keywords:
- LNK4020
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e55239b90910f6c151949c53939d4f8ed7c15c5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570694"
---
# <a name="linker-tools-warning-lnk4020"></a>リンカー ツールの警告 LNK4020

> 型レコード '*filename*' が破損しています一部のシンボルよぶ型をデバッガーからはアクセスできない可能性があります。

PDB ファイル*filename*が破損している型のレコードです。

この問題は、セカンダリを他のビルドの問題です。 多くの場合これは最初の報告されたビルドの問題でない限り、その他のエラーと警告に対処先頭。 最初の報告された問題である場合は、ビルド ディレクトリを消去し、プロジェクトをリビルドする必要があります。 並行ビルド プロセスを使用する場合は、ビルドがシリアル化する際にエラーが解決しないかどうかを参照してください。