---
description: 詳細については、「プロジェクトビルドエラー PRJ0032」を参照してください。
title: プロジェクト ビルド エラー PRJ0032
ms.date: 11/04/2016
f1_keywords:
- PRJ0032
helpviewer_keywords:
- PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
ms.openlocfilehash: 25c8f9480e63a8afee23c880912e17632111a4c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241145"
---
# <a name="project-build-error-prj0032"></a>プロジェクト ビルド エラー PRJ0032

プロジェクトレベルのカスタムビルドステップの [出力] プロパティには、' macro_expansion ' に評価される ' macro ' が含まれていました。

プロジェクトのカスタムビルドステップで、マクロの評価に問題がある可能性があるため、正しくない出力がありました。 このエラーは、パスの形式が正しくないことを意味する場合もあります。これは、ファイルパスで無効な文字または文字の組み合わせが含まれていることを意味します。

このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 評価されたパスは、プロジェクトディレクトリからの絶対パスです。
