---
title: propput |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.propput
dev_langs:
- C++
helpviewer_keywords:
- propput attribute
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5c8d9038fc8ded02afe02169731692b290466df6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442813"
---
# <a name="propput"></a>propput

プロパティ設定関数を指定します。

## <a name="syntax"></a>構文

```cpp
[propput]
```

## <a name="remarks"></a>Remarks

**Propput** C++ 属性と同じ機能を持つ、 [propput](/windows/desktop/Midl/propput) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[バインド可能な](../windows/bindable.md)の使用サンプル**propput**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`propget`, `propputref`|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[メソッド属性](../windows/method-attributes.md)<br/>
[propget](../windows/propget.md)<br/>
[propputref](../windows/propputref.md)