---
description: '詳細情報: コンパイラの警告 (レベル 2) C4653'
title: コンパイラの警告 (レベル 2) C4653
ms.date: 11/04/2016
f1_keywords:
- C4653
helpviewer_keywords:
- C4653
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
ms.openlocfilehash: bf7b2e453d4f9ea90f8b0c187fa834938de15f5a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173494"
---
# <a name="compiler-warning-level-2-c4653"></a>コンパイラの警告 (レベル 2) C4653

コンパイラオプション ' option ' はプリコンパイル済みヘッダーと矛盾しています。現在のコマンドラインオプションは無視されます

プリコンパイル済みヘッダーの使用 ([/yu](../../build/reference/yu-use-precompiled-header-file.md)) オプションで指定されたオプションは、プリコンパイル済みヘッダーが作成されたときに指定されたオプションと一致しませんでした。 このコンパイルでは、プリコンパイル済みヘッダーの作成時に指定されたオプションが使用されていました。

この警告は、プリコンパイル済みヘッダーのコンパイル時に Pack 構造体オプション ([/zp](../../build/reference/zp-struct-member-alignment.md)) に別の値が指定された場合に発生することがあります。
