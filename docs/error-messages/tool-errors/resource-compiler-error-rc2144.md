---
title: リソース コンパイラ エラー RC2144 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2144
dev_langs:
- C++
helpviewer_keywords:
- RC2144
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62f9eb2b25919a2336c36a459ef41eece447a490
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080494"
---
# <a name="resource-compiler-error-rc2144"></a>リソース コンパイラ エラー RC2144

主言語 ID が数字ではありません。

主言語 ID は 16 進数の言語 ID にする必要があります。 参照してください[言語と国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)で、*ランタイム ライブラリ リファレンス*有効な言語 Id の一覧についてはします。

このエラーは、ツールを使用して、.RC ファイルにリソースを追加してから削除した場合にも発生することがあります。 この問題を解決するには、.RC ファイルをテキスト エディターで開き、使用されていないすべてのリソースを手動でクリーンアップします。