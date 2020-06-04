---
title: リンカ ツール エラー LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: 02e80de5c34809a331003f3b0fb28d32e138a531
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194734"
---
# <a name="linker-tools-error-lnk2017"></a>リンカ ツール エラー LNK2017

' segment ' への ' symbol ' 再配置は/LARGEADDRESSAWARE がないため無効です: NO

32ビットのアドレスを使用して64ビットのイメージを構築しようとしています。 これには、次の操作が必要です。

- 固定の読み込みアドレスを使用します。

- イメージを 3 GB に制限します。

- [/Largeaddressaware: no](../../build/reference/largeaddressaware-handle-large-addresses.md)を指定します。
