---
description: 詳細については、「プロジェクトビルドエラー PRJ0024」を参照してください。
title: プロジェクト ビルド エラー PRJ0024
ms.date: 08/27/2018
f1_keywords:
- PRJ0024
helpviewer_keywords:
- PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
ms.openlocfilehash: e42df62181d02cf8d4696cc4f48afcec52cd4d76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150463"
---
# <a name="project-build-error-prj0024"></a>プロジェクト ビルド エラー PRJ0024

> Unicode パス '*path*' をユーザーの ANSI コードページに変換できませんでした。

*path* は、パス文字列の元の Unicode バージョンです。 このエラーは、現在のシステムコードページで ANSI に直接変換できない Unicode パスがある場合に発生する可能性があります。

このエラーは、コンピューター上にないコードページを使用してシステム上で開発されたプロジェクトで作業している場合に発生する可能性があります。

このエラーを解決するには、ANSI テキストを使用するようにパスを更新するか、コンピューターにコードページをインストールして、システムの既定値として設定します。
