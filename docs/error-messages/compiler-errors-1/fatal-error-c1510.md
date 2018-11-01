---
title: 致命的なエラー C1510
ms.date: 04/11/2017
f1_keywords:
- C1510
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
ms.openlocfilehash: f05f79ea78958a7d7a64f24bdce2d1151b93cdfb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596236"
---
# <a name="fatal-error-c1510"></a>致命的なエラー C1510

言語リソース clui.dll を開くことができません

コンパイラは、言語リソース DLL を読み込むことができません。

この問題の 2 つの一般的な原因があります。 32 ビットのコンパイラおよびツールを使用する場合は、大規模なプロジェクトをリンク中に 2 GB を超えるメモリを使用するには、このエラーを参照してください可能性があります。 64 ビット Windows システムで解決策は、64 ビット ネイティブを使用して、またはクロス コンパイラおよびツール、コードを生成することです。 これは、64 ビットのアプリで使用できるより大きなメモリ領域の利用します。 場合は、32 ビット システムで実行しているために、32 ビット コンパイラを使用する必要があります、場合によっては向上することが 3 GB にリンカーを使用可能なメモリの量。 詳細については、次を参照してください。 [4 ギガバイト チューニング: BCDEdit と Boot.ini](https://msdn.microsoft.com/library/vs/alm/bb613473)と[BCDEdit/set increaseuserva](https://msdn.microsoft.com/library/ff542202.aspx)コマンド。

その他の一般的な原因は、破損または不完全な Visual Studio のインストールです。 この場合、修復または Visual Studio を再インストールをもう一度インストーラーを実行します。
