---
title: リンカ ツール エラー LNK1264 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1264
dev_langs:
- C++
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8232e83774dc53755b77ad9c8b3bbb2a0bcc6ae6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102748"
---
# <a name="linker-tools-error-lnk1264"></a>リンカ ツール エラー LNK1264

指定された/LTCG:PGINSTRUMENT がコード生成は必要ありません。インストルメンテーションに失敗しました

**/LTCG:PGINSTRUMENT**でコンパイルされたなしの .obj ファイルが見つかりましたが、指定された[/GL](../../build/reference/gl-whole-program-optimization.md)します。 場所とリンクが失敗しました、インストルメンテーションをとることはできません。 コンパイルされるコマンド ラインで少なくとも 1 つの .obj ファイルが必要 **/GL**インストルメンテーションが発生することができるようにします。

最適化のガイド付きプロファイル (PGO) では、64 ビット コンパイラでは使用のみです。