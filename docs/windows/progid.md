---
title: progid |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.progid
dev_langs:
- C++
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fff878cfecf6eb39d689c3a17c1eab0ab5c47d4f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589200"
---
# <a name="progid"></a>progid

COM オブジェクトの ProgID を指定します。

## <a name="syntax"></a>構文

```cpp
[ progid(
   name
) ];
```

### <a name="parameters"></a>パラメーター

*name*  
オブジェクトを表す ProgID です。

Progid は、人間が判読できるバージョンの COM および ActiveX オブジェクトを識別するために使用したクラス id (CLSID) を提示します。

## <a name="remarks"></a>Remarks

**Progid** C++ 属性では、COM オブジェクトの ProgID を指定することができます。 ProgID がフォーム*name1.name2.version*します。 指定しない場合、*バージョン*ProgID の場合は、既定のバージョンは 1 です。 指定しない場合*name1.name2*、既定の名前は*classname.classname*します。 指定しない場合**progid**指定`vi_progid`、 *name1.name2*から取得されます`vi_progid`(次の連続番号) とバージョンが追加されます。

属性ブロックを使用する場合**progid**も使用しません**uuid**、コンパイラでチェックするかどうかをレジストリ、 **uuid** 、指定された存在**progid**. 場合**progid**が指定されていないバージョン (およびコクラスの名前、作成する場合) の生成に使用される、 **progid**します。

**progid**意味、`coclass`を指定する場合は、属性**progid**、指定した場合と同じことが、`coclass`と**progid**属性。

**Progid**属性によって指定された名前に自動的に登録するクラス。 生成された .idl ファイルが表示されない、 **progid**値。

この属性が ATL を使用するプロジェクト内で使用される場合、属性の動作を変更します。 上記の動作に加え、この属性で指定された情報がで使用される、`GetProgID`によって挿入関数、`coclass`属性。 詳細については、次を参照してください。、[コクラス](../windows/coclass.md)属性。

## <a name="example"></a>例

例をご覧ください[コクラス](../windows/coclass.md)の使用サンプル**progid**します。

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
[クラス属性](../windows/class-attributes.md)  
[Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)  
[ProgID キー](http://msdn.microsoft.com/library/windows/desktop/dd542719)  
