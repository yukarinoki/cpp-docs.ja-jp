---
title: プロジェクト ビルド エラー PRJ0034 |Microsoft Docs
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
ms.openlocfilehash: b271875173bf0e55d94989d60a1c8f7aaf408b2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065583"
---
# <a name="project-build-error-prj0034"></a>プロジェクト ビルド エラー PRJ0034

プロジェクト レベルのカスタムの追加の依存関係 ' プロパティはビルドに含まれる手順 'macro' と 'macro_expansion' を評価します。

プロジェクトでカスタム ビルド ステップには、おそらくマクロ評価の問題により、追加の依存関係のエラーが含まれています。 このエラーにあるパス形式が正しくない、文字またはファイル パスでは無効な文字の組み合わせを含むもします。

このエラーを解決するのには、マクロを修正するか、パスの指定を修正します。 パスには、プロジェクト ディレクトリからの絶対パスを指定します。