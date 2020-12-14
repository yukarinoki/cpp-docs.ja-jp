---
description: 詳細については、「プロジェクトビルドエラー PRJ0034」を参照してください。
title: プロジェクト ビルド エラー PRJ0034
ms.date: 11/04/2016
f1_keywords:
- PRJ0034
helpviewer_keywords:
- PRJ0034
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
ms.openlocfilehash: a5eb76b5a11cfed0789f6f5e5aca52e8215f4c5a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241067"
---
# <a name="project-build-error-prj0034"></a>プロジェクト ビルド エラー PRJ0034

プロジェクトレベルのカスタムビルドステップの [追加の依存関係] プロパティには、' macro_expansion ' に評価される ' macro ' が含まれていました。

マクロ評価の問題により、プロジェクトのカスタムビルドステップに追加の依存関係にエラーが含まれていました。 このエラーは、パスの形式が正しくないことを意味する場合もあります。これは、ファイルパスで無効な文字または文字の組み合わせが含まれていることを意味します。

このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 評価されたパスは、プロジェクトディレクトリからの絶対パスです。
