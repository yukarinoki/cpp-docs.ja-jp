---
title: リンカー ツールの警告 LNK4014 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4014
dev_langs:
- C++
helpviewer_keywords:
- LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df0a3b6f30733413a0f27c0b8daa07394bb04b07
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023112"
---
# <a name="linker-tools-warning-lnk4014"></a>リンカー ツールの警告 LNK4014

メンバー オブジェクト"objectname"が見つかりません

LIB が見つかりませんでした。`objectname`ライブラリ。

**/Remove**と **/extract**オプションが削除するか、ファイルにコピーするのにはメンバー オブジェクトの完全名が必要です。 完全な名前には、元のオブジェクト ファイルのパスが含まれます。 ライブラリ内のメンバー オブジェクトの完全名を表示するには、DUMPBIN を使用して、 [/ARCHIVEMEMBERS](../../build/reference/archivemembers.md)または LIB [/list](../../build/reference/managing-a-library.md)します。