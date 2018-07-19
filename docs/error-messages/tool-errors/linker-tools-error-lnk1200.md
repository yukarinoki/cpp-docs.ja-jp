---
title: リンカ ツール エラー LNK1200 |Microsoft ドキュメント
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
ms.openlocfilehash: ab32939c55dce5e27f907f3d23e639b24741cdc3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298825"
---
# <a name="linker-tools-error-lnk1200"></a>リンカ ツール エラー LNK1200
プログラム データベース 'filename' を読み取り中にエラー  
  
 プログラム データベース (PDB) が読み取れませんでした。  
  
 このエラーは、ファイルの破損によって発生することができます。  
  
 場合`filename`PDB は、オブジェクト ファイルの場合、ファイルを使用してオブジェクトを再コンパイル[/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)です。  
  
 場合`filename`PDB と再リンクの削除、メイン出力ファイルの PDB は、インクリメンタル リンク中にこのエラーが発生しました。