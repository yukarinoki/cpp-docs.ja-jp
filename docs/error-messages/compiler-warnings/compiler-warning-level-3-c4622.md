---
description: '詳細情報: コンパイラの警告 (レベル 3) C4622'
title: コンパイラの警告 (レベル 3) C4622
ms.date: 11/04/2016
f1_keywords:
- C4622
helpviewer_keywords:
- C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
ms.openlocfilehash: aa7ca3f2b31f369e40b5344e008655b84b13cd1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244811"
---
# <a name="compiler-warning-level-3-c4622"></a>コンパイラの警告 (レベル 3) C4622

オブジェクト ファイル 'file' でデバッグ情報はプリコンパイル済みヘッダーを作成したときに上書きされました

指定されたファイルの CodeView 情報が、(プリコンパイル済みヘッダーを使用する) [/Yu](../../build/reference/yu-use-precompiled-header-file.md) オプションを指定してコンパイルしたときに失われました。

プリコンパイル済みヘッダー ファイルを作成または使用する場合は、( [/Fo](../../build/reference/fo-object-file-name.md)を使用して) オブジェクト ファイルの名前を変更し、新しいオブジェクト ファイルを使用してリンクします。
