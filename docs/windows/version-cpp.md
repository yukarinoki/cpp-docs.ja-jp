---
title: バージョン (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.version
dev_langs:
- C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 60a5ad42f83d9e9528fd5bdc4c8d3e62254a3677
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438737"
---
# <a name="version-c"></a>version (C++)

クラスの複数のバージョン間で特定のバージョンを識別します。

## <a name="syntax"></a>構文

```cpp
[ version(
   "version"
) ]
```

### <a name="parameters"></a>パラメーター

*version*<br/>
バージョン番号、`coclass`します。 指定しない場合、1.0 は .idl ファイルに配置されます。

## <a name="remarks"></a>Remarks

**バージョン**C++ 属性と同じ機能を持つ、[バージョン](/windows/desktop/Midl/version)MIDL 属性と、生成された .idl ファイルに渡されます。

## <a name="example"></a>例

参照してください、[バインド可能な](../windows/bindable.md)の使用サンプルの例を**バージョン**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|**coclass**|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](../windows/compiler-attributes.md)<br/>
[クラス属性](../windows/class-attributes.md)  