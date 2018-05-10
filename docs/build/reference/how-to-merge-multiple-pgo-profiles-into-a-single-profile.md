---
title: '方法: 複数の PGO プロファイルを 1 つのプロファイルにマージ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ca8fd6ef94af290d568f3186747c659b918c0fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>方法 : 複数の PGO プロファイルを単一のプロファイルにマージする

最適化のガイド付きプロファイル (PGO) は、プロファイリングが実行されているシナリオに基づく最適化されたバイナリを作成するための優れたツールです。 いくつかの重要なまだ別個のシナリオを持つアプリケーションがある場合ですか。 複数の異なるシナリオから PGO を使用する 1 つのプロファイルを作成します。 Visual Studio で、PGO マネージャー [pgomgr.exe](pgomgr.md)、このジョブの役割をします。

プロファイルに結合の構文です。

`pgomgr /merge[:num] [.pgc_files] .pgd_files`

ここで`num`このマージによって追加された .pgc ファイルを使用するオプションの重量がします。 重みは、他のユーザーよりも重要である一部のシナリオがある場合、または複数回実行するのには、シナリオがある場合によく使用されます。

> [!NOTE]
> PGO マネージャーは、古いプロファイル データでは機能しません。 .Pgd ファイル .pgc ファイルをマージするには、.pgc ファイルを .pgd ファイルを生成したのと同じリンク呼び出しで作成された実行可能ファイルで生成される必要があります。

## <a name="examples"></a>使用例

この例では、PGO マネージャーに追加します pgcFile.pgc pgdFile.pgd 6 回。

`pgomgr /merge:6 pgcFile.pgc pgdFile.pgd`

この例では、PGO マネージャーに追加します pgcFile1.pgc と pgcFile2.pgc pgdFile.pgd、2 回の各 .pgc ファイル。

`pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd`

.Pgc ファイル引数を指定せず、PGO マネージャーを実行すると、すべての .pgc ファイルが同じ基本名の後に感嘆符 (!) とし、1 つまたは複数任意の文字の .pgd ファイルであるローカル ディレクトリを検索します。 たとえば、ローカル ディレクトリにファイル test.pgd、test!1.pgc、test2.pgc、および test!hello.pgc、し、次のコマンドが、ローカル ディレクトリから実行**pgomgr** test!1.pgc と test!hello.pgc test.pgd にマージします。

`pgomgr /merge test.pgd`

## <a name="see-also"></a>関連項目

[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)
