---
title: リンカ ツール エラー LNK1201
ms.date: 11/04/2016
f1_keywords:
- LNK1201
helpviewer_keywords:
- LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
ms.openlocfilehash: 8d02743333c02c7cdff3b75e4a16bfecda442fa9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195111"
---
# <a name="linker-tools-error-lnk1201"></a>リンカ ツール エラー LNK1201

プログラムデータベース ' filename ' に書き込み中にエラーが発生します。ディスク領域が不足しているか、パスが無効か、特権が不足していないかを確認します

リンクは、出力ファイルのプログラムデータベース (PDB) に書き込めませんでした。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ファイルが破損しています。 PDB ファイルを削除して再リンクしてください。

1. ファイルを書き込むための十分なディスク領域がありません。

1. ドライブは使用できません。ネットワークの問題が原因である可能性があります。

1. デバッガーは、リンクしようとしているプログラムでアクティブになっています。

1. ヒープ領域が不足しています。  詳細については、「 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) 」を参照してください。
