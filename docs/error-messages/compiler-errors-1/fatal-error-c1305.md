---
title: 致命的なエラー C1305
ms.date: 11/04/2016
f1_keywords:
- C1305
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
ms.openlocfilehash: 6ad00eb3d95e9f09d4f84daefb7e2a87fd1a3abf
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203360"
---
# <a name="fatal-error-c1305"></a>致命的なエラー C1305

プロファイル データベース 'pgd_fil' は異なるアーキテクチャ用です。

別のプラットフォームの/LTCG: PGINSTRUMENT 操作から生成された .pgd ファイルが[/ltcg: PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md)に渡されました。 [ガイド付き最適化のプロファイル](../../build/profile-guided-optimizations.md)は、x86 および x64 プラットフォームで使用できます。 ただし、あるプラットフォーム用に /LTCG:PGINSTRUMENT 操作によって生成された .pgd ファイルを、別のプラットフォームの /LTCG:PGOPTIMIZE への入力として使用することはできません。

このエラーを解決するには、/LTCG:PGINSTRUMENT で作成された .pgd ファイルを同じプラットフォームの /LTCG:PGOPTIMIZE に渡します。
