---
title: high_method_prefix
ms.date: 10/18/2018
f1_keywords:
- high_method_prefix
helpviewer_keywords:
- high_method_prefix attribute
ms.assetid: cacebf09-12f5-4919-ad40-939e206e340c
ms.openlocfilehash: 69e96a8a8f92316e32074a861456fffb83c79434
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616456"
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