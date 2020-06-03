---
title: リンカ ツール エラー LNK1223
ms.date: 11/04/2016
f1_keywords:
- LNK1223
helpviewer_keywords:
- LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
ms.openlocfilehash: 9c9d4c7224a7e65775354a86bd34fa9ea1b074af
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195033"
---
# <a name="linker-tools-error-lnk1223"></a>リンカ ツール エラー LNK1223

ファイルが無効かまたは壊れています: ファイルに無効な .pdata のコントリビューションが含まれています。

pdata を使用する RISC プラットフォームにおいては、コンパイラによって出力された .pdata セクションのエントリが並べ替えられていない場合に、このエラーが発生します。

この問題を解決するには、 [/gl (プログラム全体の最適化)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md)を有効にせずにコンパイルしてみてください。 また、このエラーは、関数本体が空である場合にも発生することがあります。
