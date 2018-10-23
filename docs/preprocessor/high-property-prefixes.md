---
title: high_property_prefixes |Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- high_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3932a7632b12120e722c5f375f4387e08f1853b
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49809058"
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

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)