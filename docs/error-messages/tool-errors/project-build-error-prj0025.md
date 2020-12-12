---
description: 詳細については、「プロジェクトビルドエラー PRJ0025」を参照してください。
title: プロジェクト ビルド エラー PRJ0025
ms.date: 08/27/2018
f1_keywords:
- PRJ0025
helpviewer_keywords:
- PRJ0025
ms.assetid: 57725c78-bc63-44f3-9667-2969b2d7c41d
ms.openlocfilehash: 9d7c17b9dcf8b37d14285cfd05bc92a8598f9b19
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291390"
---
# <a name="project-build-error-prj0025"></a>プロジェクト ビルド エラー PRJ0025

> バッチファイル '*file*' に、ユーザーの ANSI コードページに変換できない Unicode の内容が含まれています。
>
> *ファイルの UNICODE コンテンツ*

プロジェクトシステムは、ユーザーの現在の ANSI コードページに適切に変換できない、カスタムビルド規則またはビルドイベントに Unicode の内容を検出しました。

このエラーを解決するには、ビルドルールまたはビルドイベントの内容を更新して ANSI を使用するか、コンピューターにコードページをインストールして、システムの既定値として設定します。

カスタムビルドステップとビルドイベントの詳細については、「 [カスタムビルドステップとビルドイベント](../../build/understanding-custom-build-steps-and-build-events.md)について」を参照してください。
