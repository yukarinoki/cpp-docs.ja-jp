---
title: プロジェクトのビルドの警告 PRJ0042 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0042
dev_langs:
- C++
helpviewer_keywords:
- PRJ0042
ms.assetid: 682c9999-6f85-409f-b102-00c93243f74f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 260da8ac336c640ea875610b2c62e6c42c7d335e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211351"
---
# <a name="project-build-warning-prj0042"></a>プロジェクト ビルドの警告 PRJ0042

> 'Outputs' プロパティ ファイルのカスタム ビルド ステップの'*ファイル*' が設定されていません。 カスタム ビルド ステップはスキップされます。

出力が指定されていないために、カスタム ビルド ステップは実行されませんでした。

このエラーを解決するには、次に行ういずれか。

- カスタム ビルド ステップをビルドから除外します。

- 出力を追加します。

- カスタム ビルド ステップのコマンドの内容を削除します。