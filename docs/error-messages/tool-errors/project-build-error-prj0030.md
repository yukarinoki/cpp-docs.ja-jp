---
title: プロジェクト ビルド エラー PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: 3675c3796ae37df848e458aa2db665d8c4aa7766
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192511"
---
# <a name="project-build-error-prj0030"></a>プロジェクト ビルド エラー PRJ0030

マクロの展開エラーです。 評価の再帰は、$ (マクロ) の32レベルを超えています。

このエラーは、マクロの再帰によって発生します。 たとえば、**中間ディレクトリ**プロパティ ( [[全般] プロパティページ (プロジェクト)](../../build/reference/general-property-page-project.md)を参照) を $ (intdir) に設定した場合は、再帰が発生します。

このエラーを解決するには、定義に使用するマクロの観点からマクロまたはプロパティを定義しないでください。
