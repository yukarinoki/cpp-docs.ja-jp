---
description: '詳細情報: 致命的なエラー C1305'
title: 致命的なエラー C1305
ms.date: 11/04/2016
f1_keywords:
- C1305
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
ms.openlocfilehash: 100046d5ad7c6fa943358063d3d3cb21ffa00e5d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267899"
---
# <a name="fatal-error-c1305"></a>致命的なエラー C1305

プロファイル データベース 'pgd_fil' は異なるアーキテクチャ用です。

別のプラットフォームの/LTCG: PGINSTRUMENT 操作から生成された .pgd ファイルが [/ltcg: PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md) に渡されました。 [ガイド付き最適化のプロファイル](../../build/profile-guided-optimizations.md) は、x86 および x64 プラットフォームで使用できます。 ただし、あるプラットフォーム用に /LTCG:PGINSTRUMENT 操作によって生成された .pgd ファイルを、別のプラットフォームの /LTCG:PGOPTIMIZE への入力として使用することはできません。

このエラーを解決するには、/LTCG:PGINSTRUMENT で作成された .pgd ファイルを同じプラットフォームの /LTCG:PGOPTIMIZE に渡します。
