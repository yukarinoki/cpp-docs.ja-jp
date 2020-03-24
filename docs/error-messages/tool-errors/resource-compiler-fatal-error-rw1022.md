---
title: リソース コンパイラの致命的なエラー RW1022
ms.date: 11/04/2016
f1_keywords:
- RW1022
helpviewer_keywords:
- RW1022
ms.assetid: 6747c8a9-9c9b-4422-b414-0645d22092d0
ms.openlocfilehash: 896eac8bcc59ef84dc1437fba00c42c6c9304bed
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172751"
---
# <a name="resource-compiler-fatal-error-rw1022"></a>リソース コンパイラの致命的なエラー RW1022

**ファイル書き込み中の i/o エラー**

リソース コンパイラは、ファイルに書き込めませんでした。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ディスク領域が不足しています。 空き領域は、作成する実行可能ファイルのサイズの少なくとも2倍にする必要があります。

1. ボリュームが読み取り専用です。

1. 正しくないセクターです。

1. 共有違反です。
