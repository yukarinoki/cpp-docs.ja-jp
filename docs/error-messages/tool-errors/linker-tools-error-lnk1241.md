---
title: リンカ ツール エラー LNK1241 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1241
dev_langs:
- C++
helpviewer_keywords:
- LNK1241
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4c11a97dd99515ff7623b77ff31de5fb8577b5d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040623"
---
# <a name="linker-tools-error-lnk1241"></a>リンカ ツール エラー LNK1241

リソース ファイル 'リソース ファイル' が既に指定されています

実行する場合、このエラーは生成**cvtres**コマンドラインから手動で更新し、結果として得られる .obj を渡すかどうか、ファイルをリンカーにさらに他の .res ファイルにします。

複数 .res ファイルを指定するには、それらを渡すすべて .res ファイルとしてリンカーをしない内から作成された .obj ファイルによって**cvtres**します。