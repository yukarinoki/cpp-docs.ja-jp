---
title: リソース コンパイラ エラー RC2144
ms.date: 11/04/2016
f1_keywords:
- RC2144
helpviewer_keywords:
- RC2144
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
ms.openlocfilehash: 1b080916642fc1be4b22820668c4cb4137675425
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191198"
---
# <a name="resource-compiler-error-rc2144"></a>リソース コンパイラ エラー RC2144

主言語 ID が数字ではありません。

主言語 ID は 16 進数の言語 ID にする必要があります。 有効な言語 ID の一覧については、「 [ランタイム ライブラリ リファレンス](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) 」の「 *言語および国/地域識別文字列* 」を参照してください。

このエラーは、ツールを使用して、.RC ファイルにリソースを追加してから削除した場合にも発生することがあります。 この問題を解決するには、.RC ファイルをテキスト エディターで開き、使用されていないすべてのリソースを手動でクリーンアップします。
