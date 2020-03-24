---
title: プロジェクト ビルド エラー PRJ0006
ms.date: 11/04/2016
f1_keywords:
- PRJ0006
helpviewer_keywords:
- PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
ms.openlocfilehash: 816355276a203adba1401841ce02eb94a18085b6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192784"
---
# <a name="project-build-error-prj0006"></a>プロジェクト ビルド エラー PRJ0006

一時ファイル ' file ' を開けませんでした。 ファイルが存在し、ディレクトリが書き込み禁止になっていないことを確認します。

ビジュアルC++では、ビルド処理中に一時ファイルを作成できませんでした。 この原因には、

- 一時ディレクトリがありません。

- 読み取り専用の temp ディレクトリ。

- ディスク領域が不足しています。

- $ (IntDir) フォルダーは読み取り専用か、読み取り専用の一時ファイルが含まれています。

このエラーは、エラー PRJ0007: 出力ディレクトリ ' directory ' を作成できなかった場合にも発生します。 エラー PRJ0007 は、$ (IntDir) ディレクトリを作成できなかったことを意味します。一時的なファイルの作成も失敗します。

一時ファイルは、次のように指定するたびに作成されます。

- 応答ファイル。

- カスタムビルドステップ。

- ビルドイベント。
