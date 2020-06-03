---
title: リンカー ツールの警告 LNK4014
ms.date: 11/04/2016
f1_keywords:
- LNK4014
helpviewer_keywords:
- LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
ms.openlocfilehash: 5de53abc2342e3ed743f6b4abb871e05606dfc37
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194279"
---
# <a name="linker-tools-warning-lnk4014"></a>リンカー ツールの警告 LNK4014

メンバーオブジェクト "objectname" が見つかりません

ライブラリに `objectname` が見つかりませんでした。

**/Remove**オプションと **/extract**オプションには、削除するかファイルにコピーするメンバーオブジェクトの完全な名前が必要です。 完全な名前には、元のオブジェクトファイルのパスが含まれます。 ライブラリ内のメンバーオブジェクトの完全な名前を表示するには、DUMPBIN [/ARCHIVEMEMBERS](../../build/reference/archivemembers.md)または LIB [/list](../../build/reference/managing-a-library.md)を使用します。
