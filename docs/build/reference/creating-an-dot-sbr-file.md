---
title: 作成します。Sbr ファイル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac872dd13458c3fe15971f30a72b06e5510c5bd0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723685"
---
# <a name="creating-an-sbr-file"></a>.sbr ファイルの作成

BSCMAKE の入力ファイルは、.sbr ファイルです。 コンパイラは、コンパイルされる各オブジェクト ファイル (.obj) の .sbr ファイルを作成します。 ビルドまたはブラウザー情報ファイルを更新すると、プロジェクトのすべての .sbr ファイルをディスク上にある必要があります。

すべての可能な情報を含む .sbr ファイルを作成するには、指定[/FR](../../build/reference/fr-fr-create-dot-sbr-file.md)します。

ローカル シンボルを含まない .sbr ファイルを作成するには、指定[/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)します。 .Sbr ファイルにローカル シンボルが含まれている場合でも削除できます .bsc ファイルから BSCMAKE を使用して[/El オプション](../../build/reference/bscmake-options.md)`.`

完全なコンパイルを実行せず、.sbr ファイルを作成できます。 たとえば、/Zs 構文チェックを実行し、まだ/FR または/fr を指定する場合、.sbr ファイルを生成するコンパイラ オプションを指定できます。

ビルド プロセスは、.sbr ファイルをパックして、参照されていない定義を削除する場合より効率的にすることはできます。 コンパイラは、.sbr ファイルを自動的にパックします。

## <a name="see-also"></a>関連項目

[.bsc ファイルのビルド](../../build/reference/building-a-dot-bsc-file.md)