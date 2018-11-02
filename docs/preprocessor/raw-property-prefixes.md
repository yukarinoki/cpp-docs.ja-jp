---
title: raw_property_prefixes
ms.date: 10/18/2018
f1_keywords:
- raw_property_prefixes
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
ms.openlocfilehash: 1e44b5265e486f0e5b5896bed41b62ebbdaa4fd3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647137"
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes

**C++ 固有の仕様**

3 つのプロパティ メソッドの代替プレフィックスを指定します。

## <a name="syntax"></a>構文

```
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")
```

### <a name="parameters"></a>パラメーター

*GetPrefix*<br/>
使用するプレフィックス、`propget`メソッド。

*PutPrefix*<br/>
使用するプレフィックス、`propput`メソッド。

*PutRefPrefix*<br/>
使用するプレフィックス、`propputref`メソッド。

## <a name="remarks"></a>Remarks

既定では、低レベルで`propget`、 `propput`、および`propputref`メソッドは、というプレフィックスを持つメンバー関数によって公開**get _**、 **put _**、および**putref _** それぞれします。 これらのプレフィックスは、MIDL によって生成されるヘッダー ファイルで使用される名前と互換性があります。

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)