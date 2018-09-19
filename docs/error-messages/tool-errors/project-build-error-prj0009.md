---
title: プロジェクト ビルド エラー PRJ0009 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0009
dev_langs:
- C++
helpviewer_keywords:
- PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: efeb110823e801dd86a503a7069c4898f400769e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057185"
---
# <a name="project-build-error-prj0009"></a>プロジェクト ビルド エラー PRJ0009

ビルド ログを書き込むのために開けませんでした。

**ファイルが別のプロセスによって開かれていないと、書き込み保護されていないことを確認してください。**

設定した後、**ビルドのログ**プロパティを**はい**ビルドまたはリビルドを実行する Visual C なしで排他モードでビルド ログを開くことができません。

検査、**ビルドのログ**設定を開いて、**オプション** ダイアログ ボックス (上、**ツール** メニューのをクリックして**オプション**コマンド) し、選択**VC + + ビルド**で、**プロジェクト**フォルダー。 ビルド ファイルでは、名前は buildlog.htm され、中間ディレクトリ $(IntDir) に書き込まれます。

このエラーの考えられる理由:

- Visual C の 2 つのプロセスを実行して同時に同じ構成の両方で同じプロジェクトをビルドしようとしています。

- ビルド ログ ファイルは、ファイルをロックするプロセスで開かれます。

- ユーザーには、ファイルを作成するためのアクセス許可がありません。

- 現在のユーザーには、BuildLog.htm ファイルに書き込みアクセス権がありません。