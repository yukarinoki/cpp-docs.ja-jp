---
title: プロジェクト ビルド エラー PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: aa1c8539247287f7644742857c3cb7de321a20a2
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811477"
---
# <a name="project-build-error-prj0030"></a>プロジェクト ビルド エラー PRJ0030

マクロ拡張エラーです。 $ (マクロ) を超えました再帰 32 レベルを評価します。

このエラーは、マクロ内の再帰によって発生します。 たとえば、設定した場合、**中間ディレクトリ**プロパティ (を参照してください[[全般] プロパティ ページ (プロジェクト)](../../build/reference/general-property-page-project.md)) に $(IntDir)、再帰が。

このエラーを解決するのには、マクロまたはマクロの定義に使用するプロパティ定義されません。