---
description: '詳細情報: コンパイラの警告 (レベル 1) C4650'
title: コンパイラの警告 (レベル 1) C4650
ms.date: 11/04/2016
f1_keywords:
- C4650
helpviewer_keywords:
- C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
ms.openlocfilehash: 8af31cb6eaacc8b090103a2a5f622eb7aff275a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318885"
---
# <a name="compiler-warning-level-1-c4650"></a>コンパイラの警告 (レベル 1) C4650

デバッグ情報がプリコンパイル済みヘッダーにありません。ヘッダーからのグローバルシンボルのみを使用できます

プリコンパイル済みヘッダーファイルは、Microsoft シンボリックデバッグ情報を使用してコンパイルされませんでした。

リンクされている場合、生成された実行可能ファイルまたはダイナミックリンクライブラリファイルには、プリコンパイル済みヘッダーに含まれるローカルシンボルのデバッグ情報は含まれません。

この警告を回避するには、プリコンパイル済みヘッダーファイルを [/zi](../../build/reference/z7-zi-zi-debug-information-format.md) コマンドラインオプションで再コンパイルします。
