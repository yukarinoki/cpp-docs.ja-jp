---
title: リンカ ツール エラー LNK1264
ms.date: 11/04/2016
f1_keywords:
- LNK1264
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
ms.openlocfilehash: 00041e677ac7b69df9981551ee3b6cc18f9eb33d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183762"
---
# <a name="linker-tools-error-lnk1264"></a>リンカ ツール エラー LNK1264

/LTCG: PGINSTRUMENT が指定されましたが、コード生成は必要ありません。インストルメンテーションに失敗しました

**/Ltcg: PGINSTRUMENT**が指定されましたが、 [/gl](../../build/reference/gl-whole-program-optimization.md)を使用してコンパイルされた .obj ファイルが見つかりませんでした。 インストルメンテーションを実行できず、リンクに失敗しました。 インストルメンテーションが発生するように、 **/gl**を使用してコンパイルされたコマンドラインには、少なくとも1つの .obj ファイルが必要です。

ガイド付き最適化のプロファイル (PGO) は、64ビットのコンパイラでのみ使用できます。
