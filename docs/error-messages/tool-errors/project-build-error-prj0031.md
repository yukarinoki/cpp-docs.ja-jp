---
description: 詳細については、「プロジェクトビルドエラー PRJ0031」を参照してください。
title: プロジェクト ビルド エラー PRJ0031
ms.date: 11/04/2016
f1_keywords:
- PRJ0031
helpviewer_keywords:
- PRJ0031
ms.assetid: b42435c6-e570-4f8e-9ad5-12a7ea69ccb2
ms.openlocfilehash: 9b7d9a030cd590a750a5ad2da0329a4bf48960a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241158"
---
# <a name="project-build-error-prj0031"></a>プロジェクト ビルド エラー PRJ0031

ファイル ' file ' のカスタムビルドステップの ' Outputs ' プロパティには、' macro_expansion ' に評価される ' macro ' が含まれていました。

ファイルのカスタムビルドステップで、マクロの評価に問題がある可能性があるため、正しくない出力がありました。 このエラーは、パスの形式が正しくないことを意味する場合もあります。これは、ファイルパスで無効な文字または文字の組み合わせが含まれていることを意味します。

このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 評価されたパスは、プロジェクトディレクトリからの絶対パスです。
