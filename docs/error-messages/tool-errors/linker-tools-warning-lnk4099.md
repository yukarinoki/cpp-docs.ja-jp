---
title: リンカー ツールの警告 LNK4099
ms.date: 11/04/2016
f1_keywords:
- LNK4099
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
ms.openlocfilehash: b1f330924b8e47e0649268142106a050c83cb20a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183320"
---
# <a name="linker-tools-warning-lnk4099"></a>リンカー ツールの警告 LNK4099

PDB ' filename ' が ' object/library ' または ' path ' で見つかりませんでした。デバッグ情報がない場合と同様にオブジェクトをリンクしています

リンカーは .pdb ファイルを見つけることができませんでした。 `object/library`が格納されているディレクトリにコピーします。

オブジェクトファイルに関連付けられた .pdb ファイルの名前を検索するには、次のようにします。

1. [Lib](../../build/reference/lib-reference.md) **/extract:** `objectname` **.obj** `xyz`ライブラリからオブジェクトファイルを抽出し**ます。**

1. **Dumpbin/section:. debug $ T/rawdata** `objectname`の .pdb ファイルへのパスを確認し**ます。**

また、 [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)を使用してコンパイルして、pdb を使用する必要がないようにするか、リンクするオブジェクトの .pdb ファイルがない場合は、 [/debug](../../build/reference/debug-generate-debug-info.md)リンカーオプションを削除することもできます。
