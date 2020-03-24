---
title: コンパイラの警告 (レベル 1) C4650
ms.date: 11/04/2016
f1_keywords:
- C4650
helpviewer_keywords:
- C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
ms.openlocfilehash: e57f1d9acba4a8734339f3b8e538120abe542efc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199569"
---
# <a name="compiler-warning-level-1-c4650"></a>コンパイラの警告 (レベル 1) C4650

デバッグ情報がプリコンパイル済みヘッダーにありません。ヘッダーからのグローバルシンボルのみを使用できます

プリコンパイル済みヘッダーファイルは、Microsoft シンボリックデバッグ情報を使用してコンパイルされませんでした。

リンクされている場合、生成された実行可能ファイルまたはダイナミックリンクライブラリファイルには、プリコンパイル済みヘッダーに含まれるローカルシンボルのデバッグ情報は含まれません。

この警告を回避するには、プリコンパイル済みヘッダーファイルを[/zi](../../build/reference/z7-zi-zi-debug-information-format.md)コマンドラインオプションで再コンパイルします。
