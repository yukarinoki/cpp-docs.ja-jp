---
title: プロジェクト ビルド エラー PRJ0032
ms.date: 11/04/2016
f1_keywords:
- PRJ0032
helpviewer_keywords:
- PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
ms.openlocfilehash: 62efa0e72c6fbe4bd38983ff0507923392427c04
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192485"
---
# <a name="project-build-error-prj0032"></a>プロジェクト ビルド エラー PRJ0032

プロジェクトレベルのカスタムビルドステップの [出力] プロパティには、' macro_expansion ' に評価される ' macro ' が含まれていました。

プロジェクトのカスタムビルドステップで、マクロの評価に問題がある可能性があるため、正しくない出力がありました。 このエラーは、パスの形式が正しくないことを意味する場合もあります。これは、ファイルパスで無効な文字または文字の組み合わせが含まれていることを意味します。

このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 評価されたパスは、プロジェクトディレクトリからの絶対パスです。
