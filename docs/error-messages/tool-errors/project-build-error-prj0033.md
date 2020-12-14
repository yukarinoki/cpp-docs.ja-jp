---
description: 詳細については、「プロジェクトビルドエラー PRJ0033」を参照してください。
title: プロジェクト ビルド エラー PRJ0033
ms.date: 11/04/2016
f1_keywords:
- PRJ0033
helpviewer_keywords:
- PRJ0033
ms.assetid: 84d4a052-0586-4b78-9315-81c1e8386c1e
ms.openlocfilehash: 7faf69cd9aaed6f90d9c546c4fc2383fd6808419
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241132"
---
# <a name="project-build-error-prj0033"></a>プロジェクト ビルド エラー PRJ0033

ファイル ' file ' のカスタムビルドステップの [追加の依存関係] プロパティには、' macro_expansion ' に評価される ' macro ' が含まれていました。

ファイルのカスタムビルドステップには、マクロ評価の問題のため、追加の依存関係にエラーが含まれていました。 このエラーは、パスの形式が正しくないことを意味する場合もあります。これは、ファイルパスで無効な文字または文字の組み合わせが含まれていることを意味します。

このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 評価されたパスは、プロジェクトディレクトリからの絶対パスです。
