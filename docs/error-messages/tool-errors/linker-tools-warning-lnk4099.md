---
description: 詳細については、「リンカーツールの警告 LNK4099」を参照してください。
title: リンカー ツールの警告 LNK4099
ms.date: 11/04/2016
f1_keywords:
- LNK4099
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
ms.openlocfilehash: 1e063cce9c884b8952e4bd5807b0d4a7683d4d54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133771"
---
# <a name="linker-tools-warning-lnk4099"></a>リンカー ツールの警告 LNK4099

PDB ' filename ' が ' object/library ' または ' path ' で見つかりませんでした。デバッグ情報がない場合と同様にオブジェクトをリンクしています

リンカーは .pdb ファイルを見つけることができませんでした。 を格納しているディレクトリにコピー `object/library` します。

オブジェクトファイルに関連付けられた .pdb ファイルの名前を検索するには、次のようにします。

1. ライブラリから [lib](../../build/reference/lib-reference.md) **/extract:**.obj ファイルを抽出 `objectname`  `xyz` します。

1. **Dumpbin/section:. debug $ T/rawdata** を使用して .pdb ファイルへのパスを確認 `objectname` し **ます。**

また、 [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)を使用してコンパイルして、pdb を使用する必要がないようにするか、リンクするオブジェクトの .pdb ファイルがない場合は、 [/debug](../../build/reference/debug-generate-debug-info.md) リンカーオプションを削除することもできます。
