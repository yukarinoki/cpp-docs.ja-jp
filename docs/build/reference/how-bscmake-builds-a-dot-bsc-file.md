---
description: 詳細については、「BSCMAKE でをビルドする方法」を参照してください。Bsc ファイル
title: BSCMAKE による .bsc ファイルのビルド方法
ms.date: 11/04/2016
helpviewer_keywords:
- browse information files (.bsc), building
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
ms.openlocfilehash: 6d468f365f7f42be2eb393e53d72053b682ec65a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191382"
---
# <a name="how-bscmake-builds-a-bsc-file"></a>BSCMAKE による .bsc ファイルのビルド方法

使用できる最も効率的な方法で .bsc ファイルをビルドまたはリビルドします。 潜在的な問題を回避するには、ビルドプロセスについて理解しておくことが重要です。

BSCMAKE によってブラウザー情報ファイルがビルドされると、.sbr ファイルの長さがゼロに切り詰められます。 同じファイルの後続のビルドでは、長さが 0 (または空) の .sbr ファイルによって、.sbr ファイルに新しい影響がないことが BSCMAKE に伝えられます。 ファイルのその部分の更新が不要であり、インクリメンタルビルドで十分であることを BSCMAKE に知らせることができます。 すべてのビルド中 (/n オプションが指定されていない場合)、BSCMAKE は、変更された .sbr ファイルのみを使用して、ファイルの増分更新を試みます。

BSCMAKE は、/o オプションで指定された名前を持つ .bsc ファイルを検索します。 /O が指定されていない場合、BSCMAKE では、最初の .sbr ファイルの基本名と .bsc 拡張子を持つファイルが検索されます。 ファイルが存在する場合、BSCMAKE は、影響を与える .sbr ファイルのみを使用して、ブラウザー情報ファイルのインクリメンタルビルドを実行します。 ファイルが存在しない場合、BSCMAKE はすべての .sbr ファイルを使用して完全なビルドを実行します。 ビルドの規則は次のとおりです。

- 完全ビルドを成功させるには、指定したすべての .sbr ファイルが存在し、切り捨てられていない必要があります。 .Sbr ファイルが切り捨てられている場合は、BSCMAKE を実行する前に、再コンパイルまたはアセンブルによってリビルドする必要があります。

- インクリメンタルビルドを成功させるには、.bsc ファイルが存在している必要があります。 すべての影響を与える .sbr ファイルは空のファイルであっても存在する必要があり、BSCMAKE コマンドラインで指定する必要があります。 コマンドラインから .sbr ファイルを省略した場合、BSCMAKE によってファイルからのファイルの投稿が削除されます。

## <a name="see-also"></a>関連項目

[を構築します。Bsc ファイル](building-a-dot-bsc-file.md)
