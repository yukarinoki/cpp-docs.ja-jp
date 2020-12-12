---
description: 詳細については、「リンカツール Error LNK1241」を参照してください。
title: リンカ ツール エラー LNK1241
ms.date: 11/04/2016
f1_keywords:
- LNK1241
helpviewer_keywords:
- LNK1241
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
ms.openlocfilehash: abc72b70af9ab694744a91a8789207055bd1a5bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193930"
---
# <a name="linker-tools-error-lnk1241"></a>リンカ ツール エラー LNK1241

リソースファイル ' resource file ' は既に指定されています

このエラーは、コマンドラインから手動で **cvtres** を実行し、その後、その他の .res ファイルに加えて、結果として得られる .obj ファイルをリンカーに渡す場合に生成されます。

複数の .res ファイルを指定するには、 **cvtres** によって作成された .obj ファイル内ではなく、すべてを .lib ファイルとしてリンカーに渡します。
