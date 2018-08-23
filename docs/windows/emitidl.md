---
title: emitidl |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.emitidl
dev_langs:
- C++
helpviewer_keywords:
- emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 566e78820dd382a4b4e05742a410057b681d1fdc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603151"
---
# <a name="emitidl"></a>emitidl

後続のすべての IDL 属性が処理され、生成された .idl ファイル内に配置するかどうかを指定します。

## <a name="syntax"></a>構文

```cpp
[ emitidl(state, defaultimports=boolean) ];
```

### <a name="parameters"></a>パラメーター

*state*  
これらの使用可能な値のいずれか: `true`、 `false`、 `forced`、 `restricted`、 `push`、または`pop`します。

- 場合`true`、ソース コード ファイルで検出された IDL カテゴリ属性は、生成された .idl ファイルに配置されます。 既定の設定は、この**emitidl**します。

- 場合`false`、ソース コード ファイルで検出された IDL カテゴリ属性は、生成された .idl ファイル内に配置されていません。

- 場合`restricted`、IDL 属性のないファイルを[モジュール](../windows/module-cpp.md)属性。 コンパイラは、.idl ファイルを生成しません。

- 場合`forced`、後ろに続くオーバーライド`restricted`属性には、ファイルが必要です、`module`属性 IDL がある場合は、ファイルの属性します。

- `push` 現在を保存することができます**emitidl**内部へ設定**emitidl**スタック、および`pop`設定できます**emitidl**にどのような値は、内部の上部にある、**emitidl**スタック。

`defaultimports=`*ブール*\(省略可能)  
- 場合*ブール*は**true**docobj.idl が生成された .idl ファイルにインポートされます。 また、.idl ファイルと同じ名前、.h ファイルする場合`#include`、.h ファイルと同じディレクトリ内に、ソース コードが見つかった後、その .idl ファイルの import ステートメントが生成された .idl ファイルに含まれています。

- 場合*ブール*は**false**docobj.idl が生成された .idl ファイルにインポートされていません。 .Idl ファイルを明示的にインポートする必要があります[インポート](../windows/import.md)します。

## <a name="remarks"></a>Remarks

後に、 **emitidl** C++ 属性がソース コード ファイルで発生した、IDL カテゴリ属性は、生成された .idl ファイルに配置されます。 存在する場合ありません**emitidl**属性に、ソース コード ファイル内の IDL 属性は、生成された .idl ファイルに出力します。

複数存在することは**emitidl**ソース コード ファイル内の属性。 場合`[emitidl(false)];`が後ろに続くなしでファイルに発生した`[emitidl(true)];`、生成された .idl ファイルの属性は処理されません。

コンパイラが、新しいファイルを検出するたびに**emitidl**に暗黙的に設定されている**true**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](../windows/compiler-attributes.md)  
[スタンドアロン属性](../windows/stand-alone-attributes.md)  
[属性のサンプル](http://msdn.microsoft.com/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)