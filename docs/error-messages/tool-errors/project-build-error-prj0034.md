---
title: プロジェクト ビルド エラー PRJ0034
ms.date: 11/04/2016
f1_keywords:
- PRJ0034
helpviewer_keywords:
- PRJ0034
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
ms.openlocfilehash: bcb7e22d6a09e3435eb2236532101a1836c08a03
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192192"
---
# <a name="project-build-error-prj0034"></a>プロジェクト ビルド エラー PRJ0034

プロジェクトレベルのカスタムビルドステップの [追加の依存関係] プロパティには、' macro_expansion ' に評価される ' macro ' が含まれていました。

マクロ評価の問題により、プロジェクトのカスタムビルドステップに追加の依存関係にエラーが含まれていました。 このエラーは、パスの形式が正しくないことを意味する場合もあります。これは、ファイルパスで無効な文字または文字の組み合わせが含まれていることを意味します。

このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 評価されたパスは、プロジェクトディレクトリからの絶対パスです。
