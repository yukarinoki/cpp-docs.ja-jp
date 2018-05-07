---
title: プロジェクト ビルド エラー PRJ0031 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0031
dev_langs:
- C++
helpviewer_keywords:
- PRJ0031
ms.assetid: b42435c6-e570-4f8e-9ad5-12a7ea69ccb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d5ebd25c239a05c4300b574ec0d47035904187d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0031"></a>プロジェクト ビルド エラー PRJ0031
カスタム ビルドの 'Outputs' プロパティは、'macro_expansion' をファイル 'file' が含まれている 'macro' 評価を出すのステップします。  
  
 ファイルのカスタム ビルド ステップには、おそらくマクロ評価の問題により、不正な出力が必要があります。 このエラー意味する場合も、パスの形式が文字またはファイル パスに無効な文字の組み合わせを含むです。  
  
 このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 パスには、プロジェクト ディレクトリからの絶対パスを指定します。