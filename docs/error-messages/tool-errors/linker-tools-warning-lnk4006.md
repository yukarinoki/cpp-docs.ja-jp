---
title: リンカー ツールの警告 LNK4006
ms.date: 11/04/2016
f1_keywords:
- LNK4006
helpviewer_keywords:
- LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
ms.openlocfilehash: d949ba259de8e131f6191e757119b4c42effc3d4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194318"
---
# <a name="linker-tools-warning-lnk4006"></a>リンカー ツールの警告 LNK4006

シンボルは既にオブジェクトで定義されています。2番目の定義は無視されます

指定された `symbol` (修飾された形式で表示) は重複定義されています。 この警告が発生した場合、`symbol` は2回追加されますが、最初のフォームのみが使用されます。

2つのインポートライブラリを1つにマージしようとすると、この警告が表示されます。

C ランタイムライブラリを再構築する場合は、このメッセージを無視してもかまいません。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>修復の可能性がある解決策

1. 指定された `symbol` は、 [/gy](../../build/reference/gy-enable-function-level-linking.md)を使用してコンパイルすることによって作成される、パッケージ化された関数である可能性が このシンボルは複数のファイルに含まれていましたが、コンパイル間で変更されました。 `symbol`を含むすべてのファイルを再コンパイルします。

1. 異なるライブラリの2つのメンバーオブジェクトで、指定された `symbol` が異なる方法で定義されている可能性があります。

1. 絶対は2回定義されている場合があり、それぞれの定義に異なる値が設定されています。

1. ライブラリの結合時にエラーメッセージが表示された場合は、に追加されているライブラリに `symbol` が既に存在します。
