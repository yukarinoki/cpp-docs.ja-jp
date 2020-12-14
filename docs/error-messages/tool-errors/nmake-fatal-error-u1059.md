---
description: 詳細については、「NMAKE の致命的なエラー U1059」を参照してください。
title: NMAKE の致命的なエラー U1059
ms.date: 08/27/2018
f1_keywords:
- U1059
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
ms.openlocfilehash: 025ea8577814519b883e534c54ed8cf4383ef029
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283538"
---
# <a name="nmake-fatal-error-u1059"></a>NMAKE の致命的なエラー U1059

> 構文エラー: 依存に '} ' がありません

依存の検索パスが正しく指定されていませんでした。 パスにスペースが存在するか、右中かっこ (**}**) が省略されました。

依存関係のディレクトリ指定の構文は、

> **{** *ディレクトリ* **} 依存**

ここで、 *ディレクトリ* は1つ以上のパスを指定します。各パスはセミコロン (**;**) で区切られます。 スペースは使用できません。

検索パスの一部またはすべてがマクロで置き換えられている場合は、マクロの展開にスペースが存在しないことを確認してください。
