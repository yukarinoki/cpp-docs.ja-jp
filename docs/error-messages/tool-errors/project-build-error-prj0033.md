---
title: プロジェクト ビルド エラー PRJ0033
ms.date: 11/04/2016
f1_keywords:
- PRJ0033
helpviewer_keywords:
- PRJ0033
ms.assetid: 84d4a052-0586-4b78-9315-81c1e8386c1e
ms.openlocfilehash: 141355ac49ec4722e85b5d4c25240e8048a72c9a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192196"
---
# <a name="project-build-error-prj0033"></a>プロジェクト ビルド エラー PRJ0033

ファイル ' file ' のカスタムビルドステップの [追加の依存関係] プロパティには、' macro_expansion ' に評価される ' macro ' が含まれていました。

ファイルのカスタムビルドステップには、マクロ評価の問題のため、追加の依存関係にエラーが含まれていました。 このエラーは、パスの形式が正しくないことを意味する場合もあります。これは、ファイルパスで無効な文字または文字の組み合わせが含まれていることを意味します。

このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 評価されたパスは、プロジェクトディレクトリからの絶対パスです。
