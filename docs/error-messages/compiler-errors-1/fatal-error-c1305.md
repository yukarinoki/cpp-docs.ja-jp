---
title: 致命的なエラー C1305 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1305
dev_langs:
- C++
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 90d73003d9f19eb41f9eb34cd47c7b90b1e6164f
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42539058"
---
# <a name="fatal-error-c1305"></a>致命的なエラー C1305
プロファイル データベース 'pgd_fil' は異なるアーキテクチャ用です。  
  
 渡された別のプラットフォーム用に/LTCG:PGINSTRUMENT 操作から生成された .pgd ファイル[/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)します。 [プロファイル ガイド付き最適化の](../../build/reference/profile-guided-optimizations.md)x86 および x64 プラットフォームで利用できます。 ただし、あるプラットフォーム用に /LTCG:PGINSTRUMENT 操作によって生成された .pgd ファイルを、別のプラットフォームの /LTCG:PGOPTIMIZE への入力として使用することはできません。  
  
 このエラーを解決するには、/LTCG:PGINSTRUMENT で作成された .pgd ファイルを同じプラットフォームの /LTCG:PGOPTIMIZE に渡します。