---
title: リンカ ツール エラー LNK1200
ms.date: 11/04/2016
f1_keywords:
- LNK1200
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
ms.openlocfilehash: 9dcc37bd74a25e29726529346b1578bb8b18ac3e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195137"
---
# <a name="linker-tools-error-lnk1200"></a>リンカ ツール エラー LNK1200

プログラムデータベース ' filename ' の読み取り中にエラーが発生した

プログラムデータベース (PDB) を読み取れませんでした。

このエラーは、ファイルの破損によって発生する可能性があります。

`filename` がオブジェクトファイルの PDB である場合は、 [/zi](../../build/reference/z7-zi-zi-debug-information-format.md)を使用してオブジェクトファイルを再コンパイルします。

`filename` がメイン出力ファイルの PDB であり、インクリメンタルリンク中にこのエラーが発生した場合は、PDB を削除して再リンクします。
