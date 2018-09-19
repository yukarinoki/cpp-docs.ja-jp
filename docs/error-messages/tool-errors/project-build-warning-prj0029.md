---
title: プロジェクトのビルドの警告 PRJ0029 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0029
dev_langs:
- C++
helpviewer_keywords:
- PRJ0029
ms.assetid: f02c09c6-09f3-4d44-8cd4-9a25336be1ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 854120bf6021295348ff2e28b36f7b44007017b1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026022"
---
# <a name="project-build-warning-prj0029"></a>プロジェクト ビルドの警告 PRJ0029

プロジェクト レベルのカスタム ビルド ステップに 'Outputs' プロパティが設定されていません。 カスタム ビルド ステップはスキップされます。

出力が指定されていないために、カスタム ビルド ステップは実行されませんでした。

このエラーを解決するには、次に行ういずれか。

- カスタム ビルド ステップをビルドから除外します。

- 出力を追加します。

- カスタム ビルド ステップのコマンドの内容を削除します。