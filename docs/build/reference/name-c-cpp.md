---
title: 名前 (C++) |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- name
dev_langs:
- C++
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc37a96e50c6cd5bae2cc60661db04f3b92d162b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715755"
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