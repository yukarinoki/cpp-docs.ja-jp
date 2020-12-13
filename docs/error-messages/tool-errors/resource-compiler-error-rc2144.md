---
description: 詳細については、「リソースコンパイラエラー RC2144」を参照してください。
title: リソース コンパイラ エラー RC2144
ms.date: 11/04/2016
f1_keywords:
- RC2144
helpviewer_keywords:
- RC2144
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
ms.openlocfilehash: 8b40f989e4319b16a9a983f5e4e377aeb357e8f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133511"
---
# <a name="resource-compiler-error-rc2144"></a>リソース コンパイラ エラー RC2144

主言語 ID が数字ではありません。

主言語 ID は 16 進数の言語 ID にする必要があります。 有効な言語 ID の一覧については、「 [ランタイム ライブラリ リファレンス](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) 」の「 *言語および国/地域識別文字列* 」を参照してください。

このエラーは、ツールを使用して、.RC ファイルにリソースを追加してから削除した場合にも発生することがあります。 この問題を解決するには、.RC ファイルをテキスト エディターで開き、使用されていないすべてのリソースを手動でクリーンアップします。
