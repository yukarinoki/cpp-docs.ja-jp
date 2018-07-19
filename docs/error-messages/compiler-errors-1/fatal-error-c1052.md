---
title: 致命的なエラー c1052 など |Microsoft ドキュメント
ms.custom: ''
ms.date: 05/08/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1052
dev_langs:
- C++
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8d272b71a527763245ccf7c8d69bd11a915eab7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225854"
---
# <a name="fatal-error-c1052"></a>致命的なエラー c1052 など

> プログラム データベース ファイルでは、'*filename*'、;/DEBUG:fastlink のリンカーによって生成されたコンパイラできませんこのような PDB ファイルを更新; してください削除するかまたは/Fd を使用して、別の PDB ファイル名を指定。

コンパイラはリンカーによって生成された同じプログラム データベース (PDB) ファイルを更新できないときに、 [/DEBUG:fastlink](../../build/reference/debug-generate-debug-info.md)オプションを指定します。 通常、コンパイラによって生成された PDB ファイルと、リンカーによって生成された PDB ファイルは、異なる名前を付けます。 同じ名前を使用する設定されている場合は、このエラーは発生できます。

この問題を修正するには、前に、もう一度、コンパイルするか、コンパイラによって生成されたファイルとリンカーによって生成された PDB ファイルに異なる名前を作成することができますに PDB ファイルを明示的に削除できます。

コマンドラインでコンパイラにより生成された PDB ファイル名を指定するには、使用、 [/Fd](../../build/reference/fd-program-database-file-name.md)コンパイラ オプション。 IDE で、コンパイラによって生成された PDB ファイル名を指定するには、開く、**プロパティ ページ**で、プロジェクトのダイアログ ボックス、**構成プロパティ**、 **C/C++**、 **出力ファイル** ページで、設定、**プログラム データベース ファイル名**プロパティです。 このプロパティは、既定では、`$(IntDir)vc$(PlatformToolsetVersion).pdb`です。

代わりに、リンカーによって生成された PDB ファイル名を設定することができます。 コマンドラインで、リンカーによって生成された PDB ファイル名を指定するには、使用、 [/PDB](../../build/reference/pdb-use-program-database.md)リンカー オプション。 IDE のリンカーによって生成された PDB ファイル名を指定するには、開く、**プロパティ ページ**で、プロジェクトのダイアログ ボックス、**構成プロパティ**、**リンカー**、 **デバッグ** ページで、設定、**プログラム データベース ファイルの生成**プロパティです。 既定では、このプロパティは `$(OutDir)$(TargetName).pdb` に設定されています。
