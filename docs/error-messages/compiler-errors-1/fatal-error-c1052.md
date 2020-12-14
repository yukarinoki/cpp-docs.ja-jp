---
description: '詳細情報: 致命的なエラー C1052'
title: 致命的なエラー C1052
ms.date: 05/08/2017
f1_keywords:
- C1052
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
ms.openlocfilehash: 818210cc4c3658167de30b9e666c600695389330
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251740"
---
# <a name="fatal-error-c1052"></a>致命的なエラー C1052

> プログラムデータベースファイル '*filename*' は、/debug: fastlink を使用してリンカーによって生成されました。コンパイラは、このような PDB ファイルを更新できません。これを削除するか、または/Fd を使用して別の PDB ファイル名を指定してください

コンパイラは、 [/debug: fastlink](../../build/reference/debug-generate-debug-info.md) オプションが指定されている場合に、リンカーによって生成される同じプログラムデータベース (PDB) ファイルを更新することはできません。 通常、コンパイラによって生成される PDB ファイルとリンカーによって生成される PDB ファイルの名前は異なります。 ただし、同じ名前を使用するように設定されている場合、このエラーが発生する可能性があります。

この問題を解決するには、再度コンパイルする前に PDB ファイルを明示的に削除するか、コンパイラによって生成される PDB ファイルとリンカーによって生成される PDB ファイルに対して異なる名前を作成します。

コンパイラによって生成された PDB ファイル名をコマンドラインで指定するには、 [/fd](../../build/reference/fd-program-database-file-name.md) コンパイラオプションを使用します。 コンパイラで生成された PDB ファイル名を IDE で指定するには、プロジェクトの [ **プロパティページ** ] ダイアログボックスを開き、[ **構成プロパティ**]、[ **c/c + +**]、[ **出力ファイル** ] ページで、[ **プログラムデータベースファイル名** ] プロパティを設定します。 既定では、このプロパティは `$(IntDir)vc$(PlatformToolsetVersion).pdb` です。

または、リンカーによって生成された PDB ファイル名を設定することもできます。 リンカーによって生成された PDB ファイル名をコマンドラインで指定するには、 [/pdb](../../build/reference/pdb-use-program-database.md) リンカーオプションを使用します。 リンカーによって生成された PDB ファイル名を IDE で指定するには、プロジェクトの [ **プロパティページ** ] ダイアログボックスを開き、[ **構成プロパティ**]、[ **リンカー**]、[ **デバッグ** ] ページで、[ **プログラムデータベースファイルの生成** ] プロパティを設定します。 既定では、このプロパティは `$(OutDir)$(TargetName).pdb`に設定されています。
