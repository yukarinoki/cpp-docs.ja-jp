---
title: '方法: 複数の PGO プロファイルを単一のプロファイルにマージする'
ms.date: 03/14/2018
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
ms.openlocfilehash: 451c0f30a271f5dce3974e172766da4a23340b93
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188874"
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>方法: 複数の PGO プロファイルを単一のプロファイルにマージする

ガイド付き最適化のプロファイル (PGO) は、プロファイルされたシナリオに基づいて最適化されたバイナリを作成するための優れたツールです。 ただし、複数の重要なシナリオを持つアプリケーションがある場合はどうでしょうか。 PGO で複数の異なるシナリオから使用できる 1 つのプロファイルを作成するにはどうすればよいでしょうか。 Visual Studio では、PGO Manager ([pgomgr.exe](pgomgr.md)) によってこのジョブが実行されます。

プロファイルをマージする構文は次のとおりです。

`pgomgr /merge[:num] [.pgc_files] .pgd_files`

この `num` は、このマージによって追加された .pgc ファイルに使用するオプションの重みです。 重みは、他のシナリオよりも重要なシナリオがある場合や、複数回実行されるシナリオがある場合に一般的に使用されます。

> [!NOTE]
> 古いプロファイル データでは、PGO Manager は機能しません。 .pgc ファイルを .pgd ファイルにマージするには、.pgd ファイルを生成したものと同じリンク呼び出しによって作成された実行可能ファイルを使用して、.pgc ファイルを生成する必要があります。

## <a name="examples"></a>使用例

この例では、PGO Manager によって pgcFile.pgc が pgdFile.pgd に 6 回追加されます。

`pgomgr /merge:6 pgcFile.pgc pgdFile.pgd`

この例では、PGO Manager によって、pgcFile1.pgc と pgcFile2.pgc が .pgc ファイルごとに 2 回 pgdFile.pgd に追加されます。

`pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd`

PGO Manager を .pgc ファイルの引数を指定せずに実行すると、ローカル ディレクトリで、.pgd ファイルと同じベース名の後に感嘆符 (!) が続き、その後に任意の文字が 1 文字以上続くすべての .pgc ファイルが検索されます。 たとえば、ローカル ディレクトリにファイル test.pgd、test!1.pgc、test2.pgc、および test!hello.pgc があり、次のコマンドがローカル ディレクトリから実行された場合、**pgomgr** によって test!1.pgc と test!hello.pgc が test.pgd にマージされます。

`pgomgr /merge test.pgd`

## <a name="see-also"></a>関連項目

[ガイド付き最適化のプロファイル](profile-guided-optimizations.md)
