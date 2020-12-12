---
description: 詳細については、「リンカツール Error LNK1223」を参照してください。
title: リンカ ツール エラー LNK1223
ms.date: 11/04/2016
f1_keywords:
- LNK1223
helpviewer_keywords:
- LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
ms.openlocfilehash: eb1937f253d324781834d0b6f465c79f7009787f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194060"
---
# <a name="linker-tools-error-lnk1223"></a>リンカ ツール エラー LNK1223

ファイルが無効かまたは壊れています: ファイルに無効な .pdata のコントリビューションが含まれています。

pdata を使用する RISC プラットフォームにおいては、コンパイラによって出力された .pdata セクションのエントリが並べ替えられていない場合に、このエラーが発生します。

この問題を解決するには、 [/gl (プログラム全体の最適化)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md) を有効にせずにコンパイルしてみてください。 また、このエラーは、関数本体が空である場合にも発生することがあります。
