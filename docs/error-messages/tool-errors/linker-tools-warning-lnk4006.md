---
description: 詳細については、「リンカーツールの警告 LNK4006」を参照してください。
title: リンカー ツールの警告 LNK4006
ms.date: 11/04/2016
f1_keywords:
- LNK4006
helpviewer_keywords:
- LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
ms.openlocfilehash: 526b3f380ef7e05448280094f360c145d7f21c04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332016"
---
# <a name="linker-tools-warning-lnk4006"></a>リンカー ツールの警告 LNK4006

シンボルは既にオブジェクトで定義されています。2番目の定義は無視されます

指定された `symbol` (修飾された形式で表示) は重複定義されています。 この警告が発生すると、 `symbol` が2回追加されますが、最初のフォームのみが使用されます。

2つのインポートライブラリを1つにマージしようとすると、この警告が表示されます。

C ランタイムライブラリを再構築する場合は、このメッセージを無視してもかまいません。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. 指定されたは、 `symbol` [/gy](../../build/reference/gy-enable-function-level-linking.md)を使用してコンパイルすることによって作成されたパッケージ関数である可能性があります。 このシンボルは複数のファイルに含まれていましたが、コンパイル間で変更されました。 を含むすべてのファイルを再コンパイル `symbol` します。

1. `symbol`異なるライブラリの2つのメンバーオブジェクトで、指定されたが異なる方法で定義されている可能性があります。

1. 絶対は2回定義されている場合があり、それぞれの定義に異なる値が設定されています。

1. ライブラリの結合時にエラーメッセージが表示された場合は、が `symbol` 追加されているライブラリに既に存在しています。
