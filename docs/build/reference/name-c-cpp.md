---
title: NAME (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: c4888b8f9b6dba4b826f2ee7dda7529a4bdf1586
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414500"
---
# <a name="name-cc"></a>NAME (C/C++)

メイン出力ファイルの名前を指定します。

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>Remarks

出力ファイル名を指定することは、 [/out](../../build/reference/out-output-file-name.md)リンカー オプション、およびベース アドレスを設定することは、 [/base](../../build/reference/base-base-address.md)リンカー オプション。 両方を指定すると、/アウト上書き**名前**します。

DLL をビルドする場合の名前は DLL 名のみ影響します。

## <a name="see-also"></a>関連項目

[モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)
