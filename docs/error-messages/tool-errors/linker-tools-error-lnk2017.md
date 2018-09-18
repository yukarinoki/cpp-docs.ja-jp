---
title: リンカ ツール エラー LNK2017 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2017
dev_langs:
- C++
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80af2bb6475fc37b7feba5b29bfe9c1292740286
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022451"
---
# <a name="linker-tools-error-lnk2017"></a>リンカ ツール エラー LNK2017

/largeaddressaware:no が無効です 'segment' を 'symbol' 再配置

32 ビットのアドレスを持つ 64 ビット イメージをビルドしようとしました。 これを行うには、次の必要があります。

- 固定の読み込みアドレスを使用します。

- イメージは、3 GB に制限します。

- 指定[/largeaddressaware:no](../../build/reference/largeaddressaware-handle-large-addresses.md)します。