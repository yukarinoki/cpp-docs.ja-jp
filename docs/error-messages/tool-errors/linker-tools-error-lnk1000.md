---
title: リンカ ツール エラー LNK1000 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/18/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1000
dev_langs:
- C++
helpviewer_keywords:
- LNK1000
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a01db36200995813ec4b6862e9ddd04c6f069ba
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238683"
---
# <a name="linker-tools-error-lnk1000"></a>リンカ ツール エラー LNK1000

> 不明なエラーです。テクニカル サポート オプションのドキュメントを参照してください。

エラーの状況を記録してから、問題を特定し、再現可能なテスト_ケースの作成やり直してください。 詳細を調査し、これらのエラーを報告する方法については、次を参照してください。 [Visual c ツールセットまたはドキュメントで問題を報告する方法](../../how-to-report-a-problem-with-the-visual-cpp-toolset.md)です。

標準ヘッダー ファイル (たとえば、Windows.h) と、自分のファイルが混在する場合、このエラーが発生する可能性があります。 いずれか、最初に、次に、標準ヘッダーは、独自のヘッダー ファイルに続く場合は、プリコンパイル済みヘッダーが含まれます。