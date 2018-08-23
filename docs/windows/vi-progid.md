---
title: vi_progid |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.vi_progid
dev_langs:
- C++
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d5848581b26812f322782a73d8964deee1feefb9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606975"
---
# <a name="viprogid"></a>vi_progid

ProgID のバージョンに依存しない形式を指定します。

## <a name="syntax"></a>構文

```cpp
[ vi_progid(
   name
) ];
```

### <a name="parameters"></a>パラメーター

*name*  
オブジェクトを表すバージョン依存 ProgID です。

Progid は、人間が判読できるバージョンの COM および ActiveX オブジェクトを識別するために使用したクラス id (CLSID) を提示します。

## <a name="remarks"></a>Remarks

**Vi_progid** C++ 属性では、COM オブジェクトのバージョン依存 ProgID を指定することができます。 ProgID がフォーム*name1.name2.version*します。 バージョン依存 ProgID がない、*バージョン*します。 両方を指定することは、`progid`と**vi_progid**属性を`coclass`します。 指定しない場合**vi_progid**、バージョン依存 ProgID がで指定された値、 [progid](../windows/progid.md)属性。

**vi_progid**意味、`coclass`を指定する場合は、属性**vi_progid**、指定した場合と同じことが、`coclass`と**vi_progid**属性。

**Vi_progid**属性によって指定された名前に自動的に登録するクラス。 生成された .idl ファイルには、ProgID の値は表示されません。

ATL プロジェクトでは、場合、[コクラス](../windows/coclass.md)属性が存在することも、指定された ProgID が使用、`GetVersionIndependentProgID`関数 (によって挿入された、`coclass`属性)。

## <a name="example"></a>例

参照してください、[コクラス](../windows/coclass.md)の使用サンプルの例を**vi_progid**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)  
[クラス属性](../windows/class-attributes.md)  
[ProgID キー](http://msdn.microsoft.com/library/windows/desktop/dd542719)  
