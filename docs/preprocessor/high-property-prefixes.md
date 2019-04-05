---
title: high_property_prefixes
ms.date: 10/18/2018
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: 3f8975ec9737e02bb1216166cc6c241549e95a07
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029370"
---
# <a name="highpropertyprefixes"></a>high_property_prefixes

**C++ 固有の仕様**

3 つのプロパティ メソッドの代替プレフィックスを指定します。

## <a name="syntax"></a>構文

```
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")
```

### <a name="parameters"></a>パラメーター

*GetPrefix*<br/>
使用するプレフィックス、`propget`メソッド。

*PutPrefix*<br/>
使用するプレフィックス、`propput`メソッド。

*PutRefPrefix*<br/>
使用するプレフィックス、`propputref`メソッド。

## <a name="remarks"></a>Remarks

既定では、高度なエラー処理`propget`、 `propput`、および`propputref`メソッドは、というプレフィックスを持つメンバー関数によって公開`Get`、 `Put`、および`PutRef`、それぞれします。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)