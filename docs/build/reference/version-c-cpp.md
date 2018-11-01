---
title: VERSION (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VERSION
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
ms.openlocfilehash: 98758da627390ba4c7e852905457527a343baccc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667377"
---
# <a name="version-cc"></a>VERSION (C/C++)

.Exe ファイルのヘッダーに数値を書き込むへのリンクまたは DLL に指示します。

```
VERSION major[.minor]
```

## <a name="remarks"></a>Remarks

*メジャー*と*マイナー*引数が 0 ~ 65,535 の範囲の 10 進数。 既定ではバージョン 0.0 です。

バージョン番号を指定することは、[バージョン情報](../../build/reference/version-version-information.md)(/バージョン) オプション。

## <a name="see-also"></a>関連項目

[モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)