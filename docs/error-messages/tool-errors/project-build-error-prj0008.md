---
title: プロジェクト ビルド エラー PRJ0008
ms.date: 11/04/2016
f1_keywords:
- PRJ0008
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
ms.openlocfilehash: 7d1c11ab7539f25d371c0bfbd2853b6155c9661c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192956"
---
# <a name="project-build-error-prj0008"></a>プロジェクト ビルド エラー PRJ0008

ファイル ' file ' を削除できませんでした。

**ファイルが別のプロセスによって開かれていないこと、および書き込み禁止になっていないことを確認してください。**

リビルドまたはクリーン中に、 C++ Visual は、ビルドのすべての既知の中間ファイルと出力ファイルのほか、 [[全般構成設定] プロパティページ](../../build/reference/general-property-page-project.md)の **[クリーン時に削除する拡張機能]** プロパティでワイルドカードの指定を満たすファイルもすべて削除されます。

このエラーは、ビジュアルC++がファイルを削除できない場合に表示されます。 このエラーを解決するには、ビルドを実行するユーザー用にファイルとそのディレクトリを書き込み可能にします。
