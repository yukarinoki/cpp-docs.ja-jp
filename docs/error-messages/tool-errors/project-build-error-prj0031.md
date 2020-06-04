---
title: プロジェクト ビルド エラー PRJ0031
ms.date: 11/04/2016
f1_keywords:
- PRJ0031
helpviewer_keywords:
- PRJ0031
ms.assetid: b42435c6-e570-4f8e-9ad5-12a7ea69ccb2
ms.openlocfilehash: e13236f65aaca778a297cdd2942c07b75dd701d0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192498"
---
# <a name="project-build-error-prj0031"></a>プロジェクト ビルド エラー PRJ0031

ファイル ' file ' のカスタムビルドステップの ' Outputs ' プロパティには、' macro_expansion ' に評価される ' macro ' が含まれていました。

ファイルのカスタムビルドステップで、マクロの評価に問題がある可能性があるため、正しくない出力がありました。 このエラーは、パスの形式が正しくないことを意味する場合もあります。これは、ファイルパスで無効な文字または文字の組み合わせが含まれていることを意味します。

このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 評価されたパスは、プロジェクトディレクトリからの絶対パスです。
