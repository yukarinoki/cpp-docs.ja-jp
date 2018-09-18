---
title: リンカー ツールの警告 LNK4006 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4006
dev_langs:
- C++
helpviewer_keywords:
- LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c992369d7bb3d9a3571e23c42a64bf936d5ae383
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017613"
---
# <a name="linker-tools-warning-lnk4006"></a>リンカー ツールの警告 LNK4006

オブジェクトで既に定義されているシンボル2 番目の定義は無視されます。

指定された `symbol` (修飾された形式で表示) は重複定義されています。 この警告が発生した場合に`symbol`は 2 回追加されますが、その最初のフォームのみが使用されます。

2 つのインポート ライブラリを 1 つにマージしようとする場合は、この警告を取得できます。

C ランタイム ライブラリを再構築する場合は、このメッセージを無視できます。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. 指定した`symbol`でコンパイルして作成された、パッケージ化された関数があります。 [/Gy](../../build/reference/gy-enable-function-level-linking.md)します。 このシンボルは 1 つ以上のファイルに含まれていたが、コンパイルの間で変更されました。 含まれるすべてのファイルを再コンパイル、`symbol`します。

1. 指定した`symbol`可能性がありますで定義されているが異なるさまざまなライブラリで 2 つのメンバー オブジェクトです。

1. 絶対は、可能性がありますで定義されている 2 回、それぞれの定義で別の値。

1. ライブラリを結合するときにエラー メッセージを受信した場合`symbol`に追加されているライブラリに既に存在します。