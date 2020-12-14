---
description: '詳細情報: スタブ'
title: STUB
ms.date: 11/04/2016
f1_keywords:
- STUB
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
ms.openlocfilehash: 79a2002c119bf211652e2aab51d9656b36e3d159
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230290"
---
# <a name="stub"></a>STUB

仮想デバイスドライバー (VxD) を構築するモジュール定義ファイルで使用すると、IMAGE_DOS_HEADER 構造を含むファイル名を指定できます (WINNT で定義)。H) は、既定のヘッダーではなく、仮想デバイスドライバー (VxD) で使用されます。

```
STUB:filename
```

## <a name="remarks"></a>解説

*Filename* の指定方法は、 [/スタブ](stub-ms-dos-stub-file-name.md)リンカーオプションを使用した場合と同じです。

スタブは、VxD をビルドする場合にのみ、モジュール定義ファイルで有効です。

## <a name="see-also"></a>関連項目

[Module-Definition ステートメントの規則](rules-for-module-definition-statements.md)
