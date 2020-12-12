---
description: 詳細については、「リンカーツールの警告 LNK4014」を参照してください。
title: リンカー ツールの警告 LNK4014
ms.date: 11/04/2016
f1_keywords:
- LNK4014
helpviewer_keywords:
- LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
ms.openlocfilehash: 50de7bcba93e5df93c5c81b247be788a844b7e15
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331973"
---
# <a name="linker-tools-warning-lnk4014"></a>リンカー ツールの警告 LNK4014

メンバーオブジェクト "objectname" が見つかりません

ライブラリにライブラリが見つかりませんでした `objectname` 。

**/Remove** オプションと **/extract** オプションには、削除するかファイルにコピーするメンバーオブジェクトの完全な名前が必要です。 完全な名前には、元のオブジェクトファイルのパスが含まれます。 ライブラリ内のメンバーオブジェクトの完全な名前を表示するには、DUMPBIN [/ARCHIVEMEMBERS](../../build/reference/archivemembers.md) または LIB [/list](../../build/reference/managing-a-library.md)を使用します。
