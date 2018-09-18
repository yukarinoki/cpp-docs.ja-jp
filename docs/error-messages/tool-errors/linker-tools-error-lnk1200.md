---
title: リンカ ツール エラー LNK1200 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1200
dev_langs:
- C++
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03ecd51142bf30230b6b177a36e007345e93bf2c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059317"
---
# <a name="linker-tools-error-lnk1200"></a>リンカ ツール エラー LNK1200

プログラム データベース 'filename' を読み取り中にエラー

プログラム データベース (PDB) を読み取ることができませんでした。

このエラーは、ファイルの破損によって発生することができます。

場合`filename`pdb ファイルは、オブジェクトのファイルで、ファイルを使用してオブジェクトを再コンパイル[/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)します。

場合`filename`PDB および再リンクの削除、メイン出力ファイルの PDB であり、インクリメンタル リンク中にこのエラーが発生しました。