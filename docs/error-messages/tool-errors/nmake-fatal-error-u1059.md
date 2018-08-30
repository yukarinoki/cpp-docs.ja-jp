---
title: NMAKE の致命的なエラー U1059 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1059
dev_langs:
- C++
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b54919398c757bfe05f747ff57341f31decfc61
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200791"
---
# <a name="nmake-fatal-error-u1059"></a>NMAKE の致命的なエラー U1059

> 構文エラー: '}' に依存します。

依存ファイルの検索パスが正しく指定されていません。 パスまたは右中かっこに空白が存在していた (**}**) を省略した場合します。

依存ファイルのディレクトリの指定の構文は、

> **{** *ディレクトリ* **} 依存**

場所*ディレクトリ*1 つまたは複数のパスをセミコロンで区切って指定それぞれを指定します (**;**)。 スペースは許可されません。

検索パスの一部またはすべては、マクロに置き換え場合、は、マクロ展開中にスペースが存在しないことを確認してください。