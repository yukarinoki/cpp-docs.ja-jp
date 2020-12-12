---
description: '詳細情報: バージョン (C/c + +)'
title: VERSION (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VERSION
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
ms.openlocfilehash: 1a63435c752220ab9fef54628ab101a14ef58582
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176393"
---
# <a name="version-cc"></a>VERSION (C/C++)

.Exe ファイルまたは DLL のヘッダーに番号を配置するようにリンクに指示します。

```
VERSION major[.minor]
```

## <a name="remarks"></a>解説

*Major* および *minor* 引数は、0 ~ 65535 の範囲の10進数です。 既定値は、バージョン0.0 です。

バージョン番号は、 [バージョン情報](version-version-information.md) (/VERSION) オプションを使用して指定するのと同じ方法で指定できます。

## <a name="see-also"></a>関連項目

[Module-Definition ステートメントの規則](rules-for-module-definition-statements.md)
