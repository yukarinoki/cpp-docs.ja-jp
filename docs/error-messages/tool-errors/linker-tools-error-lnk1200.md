---
description: 詳細については、「リンカツール Error LNK1200」を参照してください。
title: リンカ ツール エラー LNK1200
ms.date: 11/04/2016
f1_keywords:
- LNK1200
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
ms.openlocfilehash: b8c380b16cef47a4b340e4a48853d58d1ab203e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341647"
---
# <a name="linker-tools-error-lnk1200"></a>リンカ ツール エラー LNK1200

プログラムデータベース ' filename ' の読み取り中にエラーが発生した

プログラムデータベース (PDB) を読み取れませんでした。

このエラーは、ファイルの破損によって発生する可能性があります。

`filename`がオブジェクトファイルの PDB の場合は、 [/zi](../../build/reference/z7-zi-zi-debug-information-format.md)を使用してオブジェクトファイルを再コンパイルします。

`filename`がメイン出力ファイルの PDB であり、インクリメンタルリンク中にこのエラーが発生した場合は、pdb を削除して再リンクします。
