---
title: プロジェクト ビルド エラー PRJ0024 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0024
dev_langs:
- C++
helpviewer_keywords:
- PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb539a5f1ee5f1aa5f9d828d93fa6d0dc8690c22
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215599"
---
# <a name="project-build-error-prj0024"></a>プロジェクト ビルド エラー PRJ0024

> Unicode のパス '*パス*' ユーザーの ANSI コード ページに変換できませんでした。

*パス*パス文字列の元の Unicode バージョンです。 場合にこのエラーは発生が Unicode パスを直接に変換できない ANSI の現在のシステム コード ページ。

場合は、コンピューターではないにコード ページを使用してシステムで開発されたプロジェクトに取り組んで、このエラーが発生する可能性があります。

このエラーの解決は、ANSI テキストを使用して、または、コード ページをコンピューターにインストールし、システムの既定値として設定するパスを更新するには。