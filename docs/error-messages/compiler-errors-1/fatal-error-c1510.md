---
description: '詳細情報: 致命的なエラー C1510'
title: 致命的なエラー C1510
ms.date: 04/11/2017
f1_keywords:
- C1510
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
ms.openlocfilehash: 3112874f033fdeed4cc4290b2469105a275baed8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276323"
---
# <a name="fatal-error-c1510"></a>致命的なエラー C1510

言語リソース clui.dll を開くことができません

コンパイラは言語リソース DLL を読み込めません。

この問題には、2つの一般的な原因があります。 32ビットのコンパイラおよびツールを使用する場合、リンク中に 2 GB を超えるメモリを使用する大規模なプロジェクトでは、このエラーが発生することがあります。 64ビットの Windows システムで考えられる解決策は、64ビットのネイティブまたはクロスコンパイラとツールを使用してコードを生成することです。 これにより、64ビットアプリに使用できる大きなメモリ領域が活用されます。 32ビットシステムで実行されているために32ビットのコンパイラを使用する必要がある場合は、場合によっては、リンカーで使用可能なメモリの量を 3 GB に増やすことができます。 詳細については、「 [4 Gb チューニング: bcdedit と Boot.ini](/windows/win32/memory/4-gigabyte-tuning) 」および「 [bcdedit/set increaseuserva](/windows-hardware/drivers/devtest/bcdedit--set) コマンド」を参照してください。

その他の一般的な原因は、Visual Studio のインストールが壊れているか不完全であることです。 この場合は、インストーラーを再度実行して、Visual Studio を修復または再インストールします。
