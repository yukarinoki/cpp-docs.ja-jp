---
title: リンカー ツールの警告 LNK4099 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4099
dev_langs:
- C++
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50bdceaba2e72312febec4819b96df334b5398c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026011"
---
# <a name="linker-tools-warning-lnk4099"></a>リンカー ツールの警告 LNK4099

Pdb ファイル 'filename' の 'オブジェクト/ライブラリ' または 'path'; に見つかりませんデバッグ情報オブジェクトをリンク

リンカーは、.pdb ファイルが見つかりませんでした。 格納されているディレクトリにコピー`object/library`します。

オブジェクト ファイルに関連付けられた .pdb ファイルの名前を検索するには。

1. オブジェクト ファイルをライブラリから抽出[lib](../../build/reference/lib-reference.md) **/extract:**`objectname`**.obj** `xyz` **.lib**します。

1. .Pdb ファイルへのパスを確認してください。 **dumpbin/section:.debug$ T/rawdata** `objectname` **.obj**します。

コンパイルすることも[/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)pdb ファイルは、使用、または削除する必要があるため、 [/debug](../../build/reference/debug-generate-debug-info.md)リンカー オプションは、リンク オブジェクトの .pdb ファイルがあるない場合。