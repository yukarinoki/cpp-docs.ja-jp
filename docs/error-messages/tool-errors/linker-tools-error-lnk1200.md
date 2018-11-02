---
title: リンカ ツール エラー LNK1200
ms.date: 11/04/2016
f1_keywords:
- LNK1200
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
ms.openlocfilehash: c99b25a83836f1ee0bc6ba622e42ea382c377172
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466834"
---
# <a name="linker-tools-error-lnk1200"></a>リンカ ツール エラー LNK1200

プログラム データベース 'filename' を読み取り中にエラー

プログラム データベース (PDB) を読み取ることができませんでした。

このエラーは、ファイルの破損によって発生することができます。

場合`filename`pdb ファイルは、オブジェクトのファイルで、ファイルを使用してオブジェクトを再コンパイル[/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)します。

場合`filename`PDB および再リンクの削除、メイン出力ファイルの PDB であり、インクリメンタル リンク中にこのエラーが発生しました。