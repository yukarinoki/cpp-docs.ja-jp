---
description: 詳細については、「リンカツール Error LNK2017」を参照してください。
title: リンカ ツール エラー LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: e4215d7c1730f85f43c2440163fa03ad97c741e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338451"
---
# <a name="linker-tools-error-lnk2017"></a>リンカ ツール エラー LNK2017

' segment ' への ' symbol ' 再配置は/LARGEADDRESSAWARE がないため無効です: NO

32ビットのアドレスを使用して64ビットのイメージを構築しようとしています。 これには、次の操作が必要です。

- 固定の読み込みアドレスを使用します。

- イメージを 3 GB に制限します。

- [/Largeaddressaware: no](../../build/reference/largeaddressaware-handle-large-addresses.md)を指定します。
