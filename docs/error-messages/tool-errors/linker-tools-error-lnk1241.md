---
title: リンカ ツール エラー LNK1241
ms.date: 11/04/2016
f1_keywords:
- LNK1241
helpviewer_keywords:
- LNK1241
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
ms.openlocfilehash: 6e2b955787166c94be4ca35e1c58df5becd243f2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183814"
---
# <a name="linker-tools-error-lnk1241"></a>リンカ ツール エラー LNK1241

リソースファイル ' resource file ' は既に指定されています

このエラーは、コマンドラインから手動で**cvtres**を実行し、その後、その他の .res ファイルに加えて、結果として得られる .obj ファイルをリンカーに渡す場合に生成されます。

複数の .res ファイルを指定するには、 **cvtres**によって作成された .obj ファイル内ではなく、すべてを .lib ファイルとしてリンカーに渡します。
