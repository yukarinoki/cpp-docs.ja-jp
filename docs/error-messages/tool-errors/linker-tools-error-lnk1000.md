---
title: リンカ ツール エラー LNK1000
ms.date: 06/18/2018
f1_keywords:
- LNK1000
helpviewer_keywords:
- LNK1000
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
ms.openlocfilehash: 48b976f6e996d0e076849dc9b20b4cedd47dfbcd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195423"
---
# <a name="linker-tools-error-lnk1000"></a>リンカ ツール エラー LNK1000

> 原因不明のエラーです。テクニカルサポートオプションについては、ドキュメントを参照してください。

エラーの状況を確認し、問題を特定して、再現可能なテストケースを作成します。 これらのエラーを調査して報告する方法の詳細については、「[ビジュアルC++ツールセットまたはドキュメントで問題を報告する方法](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md)」を参照してください。

標準ヘッダーファイル (たとえば、Windows .h) と独自のファイルが混在している場合は、このエラーが発生することがあります。 プリコンパイル済みヘッダー (存在する場合)、最初に標準ヘッダー、次に独自のヘッダーファイルを含めます。
