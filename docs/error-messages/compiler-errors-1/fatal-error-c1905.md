---
title: 致命的なエラー C1905 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1905
dev_langs:
- C++
helpviewer_keywords:
- C1905
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 263bf0ff63d71f381e68ea33b294abd423f59bf4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058446"
---
# <a name="fatal-error-c1905"></a>致命的なエラー C1905

フロント エンドとバック エンドに互換性がありません (同じプロセッサを対象としなければなりません)。

このエラーは、.obj ファイルは、コンパイラ フロント エンド (C1.dll) ターゲット プロセッサ、x86、ARM、または x64、によって生成されますが異なるプロセッサを対象とするバック エンド (C2.dll) によって読み取られるときに発生します。

この問題を解決するには、一致するフロントエンドとバックエンドを使用しているか確認します。 これは、Visual Studio に作成されたプロジェクトの既定値です。 プロジェクト ファイルを編集してコンパイラ ツールへの異なるパスを使用した場合に、このエラーが表示されることがあります。 コンパイラ ツールのパスを特に設定していない場合は、Visual Studio のインストールが破損していると、このエラーが発生することがあります。 たとえば、コンパイラの .dll ファイルを 1 つの場所から別の場所にコピーした場合です。 使用**プログラムと機能**修復または Visual Studio を再インストールする Windows コントロール パネルの します。