---
title: コンパイラの警告 (レベル 3) C4622
ms.date: 11/04/2016
f1_keywords:
- C4622
helpviewer_keywords:
- C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
ms.openlocfilehash: 295a183afb24121a2abefd336f6ea92110220155
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185505"
---
# <a name="compiler-warning-level-3-c4622"></a>コンパイラの警告 (レベル 3) C4622

オブジェクト ファイル 'file' でデバッグ情報はプリコンパイル済みヘッダーを作成したときに上書きされました

指定されたファイルの CodeView 情報が、(プリコンパイル済みヘッダーを使用する) [/Yu](../../build/reference/yu-use-precompiled-header-file.md) オプションを指定してコンパイルしたときに失われました。

プリコンパイル済みヘッダー ファイルを作成または使用する場合は、( [/Fo](../../build/reference/fo-object-file-name.md)を使用して) オブジェクト ファイルの名前を変更し、新しいオブジェクト ファイルを使用してリンクします。
