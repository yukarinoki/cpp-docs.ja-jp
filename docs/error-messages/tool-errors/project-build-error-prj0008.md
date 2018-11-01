---
title: プロジェクト ビルド エラー PRJ0008
ms.date: 11/04/2016
f1_keywords:
- PRJ0008
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
ms.openlocfilehash: 696b77e9906b231a680027a3faaf23e53d8fb6e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525906"
---
# <a name="project-build-error-prj0008"></a>プロジェクト ビルド エラー PRJ0008

ファイル 'file' を削除できませんでした。

**ファイルが別のプロセスによって開かれていないと、書き込み保護されていないことを確認してください。**

Visual C には、すべて既知中間ファイルと出力ファイルのビルド、および指定したワイルドカードと一致するファイルが削除されます再構築中またはクリーン、**クリーン時に削除する拡張機能**プロパティ、[全般構成設定 プロパティ ページ](../../ide/general-property-page-project.md)します。

Visual C のファイルを削除することがない場合、このエラーが表示されます。 エラーを解決するには、ファイルとそのディレクトリを書き込み可能のビルドを実行するユーザー。