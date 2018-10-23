---
title: high_method_prefix |Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- high_method_prefix
dev_langs:
- C++
helpviewer_keywords:
- high_method_prefix attribute
ms.assetid: cacebf09-12f5-4919-ad40-939e206e340c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1fb69b9fbb7ede0ca458007aec1bee2cf38e286f
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49807719"
---
# <a name="highmethodprefix"></a>high_method_prefix

**C++ 固有の仕様**

高レベルのプロパティおよびメソッドの名前付けで使用されるプレフィックスを指定します。

## <a name="syntax"></a>構文

```
high_method_prefix("Prefix")
```

### <a name="parameters"></a>パラメーター

*Prefix*<br/>
使用されるプレフィックス。

## <a name="remarks"></a>Remarks

既定では、高度なエラー処理のプロパティとメソッドは、プレフィックスなしの名前のメンバー関数によって公開されます。 名前はタイプ ライブラリから取り込まれます。

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)