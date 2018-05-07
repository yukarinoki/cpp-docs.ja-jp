---
title: プロジェクト ビルド エラー PRJ0034 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0034
dev_langs:
- C++
helpviewer_keywords:
- PRJ0034
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a65ca2c53ba2801f861471c66f7e1f2ec8766345
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0034"></a>プロジェクト ビルド エラー PRJ0034
プロジェクト レベルのカスタムの ' Additional Dependencies プロパティは、手順が含まれている 'macro' 評価を出す 'macro_expansion' を作成します。  
  
 プロジェクトでカスタム ビルド ステップには、おそらくマクロ評価の問題により、追加の依存関係のエラーが含まれています。 このエラー意味する場合も、パスの形式が文字またはファイル パスに無効な文字の組み合わせを含むです。  
  
 このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 パスには、プロジェクト ディレクトリからの絶対パスを指定します。