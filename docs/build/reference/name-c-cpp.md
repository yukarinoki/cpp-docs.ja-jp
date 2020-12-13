---
description: '詳細情報: 名前 (C/c + +)'
title: NAME (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: 7444aa20539b47b1f04d17a266a0b65a552af3f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137775"
---
# <a name="name-cc"></a>NAME (C/C++)

メイン出力ファイルの名前を指定します。

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>解説

出力ファイル名を指定するには、 [/out](out-output-file-name.md) リンカーオプションを使用します。また、同じ方法でベースアドレスを設定する方法は、 [/base](base-base-address.md) リンカーオプションを使用する場合と同じです。 両方が指定されている場合、/OUT は **名前** をオーバーライドします。

DLL をビルドする場合、NAME は DLL 名にのみ影響します。

## <a name="see-also"></a>関連項目

[Module-Definition ステートメントの規則](rules-for-module-definition-statements.md)
