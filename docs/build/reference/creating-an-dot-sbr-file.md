---
description: 詳細については、「」を参照してください。.Sbr ファイル
title: .sbr ファイルの作成
ms.date: 11/04/2016
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
ms.openlocfilehash: 7f3e056418fe1716dc0130330b09c369e9bdceff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196920"
---
# <a name="creating-an-sbr-file"></a>.sbr ファイルの作成

> [!WARNING]
> BSCMAKE は、現在も Visual Studio と共にインストールされていますが、IDE では使用されなくなりました。 Visual Studio 2008 以降、ブラウザーとシンボルの情報は、ソリューション フォルダー内の SQL Server の .sdf ファイルに自動的に格納されます。

BSCMAKE の入力ファイルは .sbr ファイルです。 コンパイラは、コンパイルするオブジェクトファイル (.obj) ごとに .sbr ファイルを作成します。 ブラウザー情報ファイルをビルドまたは更新する場合、プロジェクトのすべての .sbr ファイルがディスク上で使用可能である必要があります。

使用可能なすべての情報を含む .sbr ファイルを作成するには、 [/fr](fr-fr-create-dot-sbr-file.md)を指定します。

ローカルシンボルを含まない .sbr ファイルを作成するには、 [/fr](fr-fr-create-dot-sbr-file.md)を指定します。 .Sbr ファイルにローカルシンボルが含まれている場合でも、BSCMAKE の[オプション](bscmake-options.md)を使用して .bsc ファイルからこれらを省略できます。`.`

完全コンパイルを実行せずに、.sbr ファイルを作成できます。 たとえば、コンパイラに対して/Zs オプションを指定して構文チェックを実行し、/FR または/Fr. を指定した場合でも .sbr ファイルを生成することができます。

参照されていない定義を削除するために .sbr ファイルを最初にパックする場合は、ビルドプロセスの方が効率的です。 このコンパイラは、.sbr ファイルを自動的にパックします。

## <a name="see-also"></a>関連項目

[を構築します。Bsc ファイル](building-a-dot-bsc-file.md)
