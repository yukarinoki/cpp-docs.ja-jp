---
title: プロジェクト ビルド エラー PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: 2a6cde4ca48acb9aadfe3109084483dbb554e1e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488076"
---
# <a name="project-build-error-prj0030"></a>プロジェクト ビルド エラー PRJ0030

マクロ拡張エラーです。 $ (マクロ) を超えました再帰 32 レベルを評価します。

このエラーは、マクロ内の再帰によって発生します。 たとえば、設定した場合、**中間ディレクトリ**プロパティ (を参照してください[[全般] プロパティ ページ (プロジェクト)](../../ide/general-property-page-project.md)) に $(IntDir)、再帰が。

このエラーを解決するのには、マクロまたはマクロの定義に使用するプロパティ定義されません。