---
description: 詳細については、「リンカツール Error LNK1000」を参照してください。
title: リンカ ツール エラー LNK1000
ms.date: 06/18/2018
f1_keywords:
- LNK1000
helpviewer_keywords:
- LNK1000
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
ms.openlocfilehash: 54692b635b83756a26490779c0205ccc5f20d3bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261607"
---
# <a name="linker-tools-error-lnk1000"></a>リンカ ツール エラー LNK1000

> 原因不明のエラーです。テクニカルサポートオプションについては、ドキュメントを参照してください。

エラーの状況を確認し、問題を特定して、再現可能なテストケースを作成します。 これらのエラーを調査して報告する方法の詳細については、「 [Visual C++ ツールセットまたはドキュメントを使用して問題を報告する方法](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md)」を参照してください。

標準ヘッダーファイル (たとえば、Windows .h) と独自のファイルが混在している場合は、このエラーが発生することがあります。 プリコンパイル済みヘッダー (存在する場合)、最初に標準ヘッダー、次に独自のヘッダーファイルを含めます。
