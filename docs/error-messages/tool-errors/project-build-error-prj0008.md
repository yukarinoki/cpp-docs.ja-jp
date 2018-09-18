---
title: プロジェクト ビルド エラー PRJ0008 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0008
dev_langs:
- C++
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7c24634a845423de590228af01cb9f4779e37ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062788"
---
# <a name="project-build-error-prj0008"></a>プロジェクト ビルド エラー PRJ0008

ファイル 'file' を削除できませんでした。

**ファイルが別のプロセスによって開かれていないと、書き込み保護されていないことを確認してください。**

Visual C には、すべて既知中間ファイルと出力ファイルのビルド、および指定したワイルドカードと一致するファイルが削除されます再構築中またはクリーン、**クリーン時に削除する拡張機能**プロパティ、[全般構成設定 プロパティ ページ](../../ide/general-property-page-project.md)します。

Visual C のファイルを削除することがない場合、このエラーが表示されます。 エラーを解決するには、ファイルとそのディレクトリを書き込み可能のビルドを実行するユーザー。