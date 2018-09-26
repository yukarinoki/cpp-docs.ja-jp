---
title: TMP_MAX、L_tmpnam | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- TMP_MAX
- L_tmpnam
dev_langs:
- C++
helpviewer_keywords:
- temporary files, length
- L_tmpnam constant
- TMP_MAX constant
ms.assetid: ab19fd0c-b5b7-49f7-b23d-da9dfbcf0c1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cee175eb7f12952dfe7e30ef79842ee03a96fbb1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019680"
---
# <a name="tmpmax-ltmpnam"></a>TMP_MAX、L_tmpnam

## <a name="syntax"></a>構文

```
#include <stdio.h>
```

## <a name="remarks"></a>コメント

`TMP_MAX` は、`tmpnam` 関数で生成できる一意のファイル名の最大数です。 `L_tmpnam` は、`tmpnam` で生成される一時ファイル名の長さです。

## <a name="see-also"></a>参照

[グローバル定数](../c-runtime-library/global-constants.md)