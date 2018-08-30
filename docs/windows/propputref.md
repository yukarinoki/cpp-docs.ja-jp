---
title: propputref |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.propputref
dev_langs:
- C++
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b0b36342b7760eea074fe15506386bb3d7ce6764
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221243"
---
# <a name="propputref"></a>propputref

値の代わりに参照を使用するプロパティ設定関数を指定します。

## <a name="syntax"></a>構文

```cpp
[propputref]
```

## <a name="remarks"></a>Remarks

**Propputref** C++ 属性と同じ機能を持つ、 [propputref](/windows/desktop/Midl/propputref) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[バインド可能な](../windows/bindable.md)の使用サンプル**propputref**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`propget`, `propput`|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[メソッド属性](../windows/method-attributes.md)  
[propget](../windows/propget.md)  
[propput](../windows/propput.md)  