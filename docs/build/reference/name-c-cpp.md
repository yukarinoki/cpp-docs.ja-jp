---
title: NAME (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: d0813befc622db72e095c449794405fc5d58465b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812188"
---
# <a name="name-cc"></a>NAME (C/C++)

メイン出力ファイルの名前を指定します。

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>Remarks

出力ファイル名を指定することは、 [/out](out-output-file-name.md)リンカー オプション、およびベース アドレスを設定することは、 [/base](base-base-address.md)リンカー オプション。 両方を指定すると、/アウト上書き**名前**します。

DLL をビルドする場合の名前は DLL 名のみ影響します。

## <a name="see-also"></a>関連項目

[モジュール定義ステートメントに関する規則](rules-for-module-definition-statements.md)
